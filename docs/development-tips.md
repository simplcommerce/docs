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
