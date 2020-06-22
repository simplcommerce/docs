# How to setup email using SendGrid

---

### 1. Uncomment the AfterOrderCreatedSendEmailHanlder registration

In the Order module, open the ModuleInitializer.cs uncomment the following line

```csharp
//services.AddTransient<INotificationHandler<AfterOrderCreated>, AfterOrderCreatedSendEmailHanlder>();
```

We are consider using feature flag. But it is for now

### 2. Add project reference

In the SimplCommerce.WebHost.csproj add project reference to the SimplCommerce.Module.EmailSenderSendgrid module. And remove other email sender modules if any.

### 3. Update modules.json

Open the modules.json in WebHost then add module EmailSenderSendgrid

```json
  {
    "id": "SimplCommerce.Module.EmailSenderSendgrid",
    "isBundledWithHost": true,
    "version": "1.0.0"
  }
```

Remove the other email sender modules if any

### 4. Add configuration for EmailSenderSendgrid module

In the appsettings.json add the following setting. Update the settings values to your

```json
  "SendGrid": {
    "ApiKey": "Your Send Grid API Key",
    "FromEmail": "no-reply@simplcommerce.com",
    "FromName": "SimplCommerce"
  }
```