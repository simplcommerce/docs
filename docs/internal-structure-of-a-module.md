# Internal structure of a module

---

![Internal module structure](images/module-internal.png)

The structure of a module is very straightforward. We just want to highlight some important notes below:

- The "Data" folder is where you will put your custom repositories or custom entity framework mapping. Normally will using the generic Repository<YourModelName> and won't need to create repository for your models. If you wish to do some custom mapping for your model, create an implementation of ICustomModelBuilder, which will automatically hooked during the startup.

- The "Events" folder is where you will put domain event handling code. We use MediatR for publishing and handling domain events such as UserSignedIn, EntityViewed, EntityDeleting. You can publish your own events and handle them.

- The "wwwroot" folder is where you will put the front-end code. For the admin pages (AngularJS), until we implement a better way, you need to register your javascript files in SimplCommerce.Module.Core/Views/HomeAdmin/Index.cshtml.

- The "Services" folder is where you will put the business logic code. For simple scenarios select, insert, update, delete. We recommend that you call repository directly in Controller, and do not need create services.

- All the IoC registrations are automatically done for you during the startup. In cases you want to to some special thing during the module initialization. You can create an implementation of IModuleInitializer


