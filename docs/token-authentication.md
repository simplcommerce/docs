# Token Authentication for API

---

Although the admin side is written as a Single Page Application with Angular, we chose cookies authentication for simplicity.

Recently we have added Identity Server 4, a mature OpenID Connect and OAuth 2.0 Framework for ASP.NET Core. 

We use [InMemory configuration](https://github.com/simplcommerce/SimplCommerce/blob/master/src/SimplCommerce.WebHost/IdentityServer/IdentityServerConfig.cs)

You can update or add new Client according to your need. With the access token you can call SimplCommerce's APIs, such as 'add products', 'categories', etc..
