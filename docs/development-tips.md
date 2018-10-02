# Development tips

---

### Using Secret Manager

The Secret Manager tool stores sensitive data during the development of an ASP.NET Core project. [See docs](https://docs.microsoft.com/en-us/aspnet/core/security/app-secrets). We recommend you use secret manager to store specific setting data for your local development such as the connection string

##### Using User Secrets Tool for Visual Studio

1. Right click the SimplCommerce.WebHost 
2. Choose "Manage User Secrets"
3. Write Your secrets in `secrets.json` as the following:
```
{
    "ConnectionStrings:DefaultConnection": "Your ConnectionString"
}
```

##### Using User Secrets Command Line Tool

```
dotnet user-secrets set "ConnectionStrings:DefaultConnection" "Your ConnectionString"
```

### Copy module

Any changes that you have made in modules need to be copied to the WebHost to be loaded. You can do this in several ways:

- Build SimplCommerce.WebHost which will trigger the custom MSBuild CopyModuleTask
- Manually run the "copy-modules" gulp task in the Task Runner Explorer
- If your changes are only .css, .js, you can simply run the "copy-static" and then refresh the browser.

![Task runner](images/taskrunner.png)

The gulp file can be found at https://github.com/simplcommerce/SimplCommerce/blob/master/src/SimplCommerce.WebHost/gulpfile.js
