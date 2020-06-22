# How to setup email using Smtp

---

### 1. Uncomment the AfterOrderCreatedSendEmailHanlder registration

In the Order module, open the ModuleInitializer.cs uncomment the following line

```csharp
//services.AddTransient<INotificationHandler<AfterOrderCreated>, AfterOrderCreatedSendEmailHanlder>();
```

### 2. Add project reference

In the SimplCommerce.WebHost.csproj add project reference to the SimplCommerce.Module.EmailSenderSmtp module. And remove other email sender modules if any.

### 3. Update modules.json

Open the modules.json in WebHost then add module EmailSenderSmtp

```json
  {
    "id": "SimplCommerce.Module.EmailSenderSmtp",
    "isBundledWithHost": true,
    "version": "1.0.0"
  }
```

Remove the other email sender modules if any

### 4. Insert or Update configuration for EmailSenderSmtp module

Open the Core_AppSetting table in the database.


|Id | Value | Module | IsVisibleInCommonSettingPage |
|----------|----------|----------|----------|
| SmtpServer | Your smtp server |EmailSenderSmtp | 0|
| SmtpPort | Your smtp port |EmailSenderSmtp | 0|
| SmtpUsername | Your smtp server username |EmailSenderSmtp | 0|
| SmtpPassword | Your smtp password |EmailSenderSmtp | 0|

