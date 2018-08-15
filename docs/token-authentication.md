# Token Authentication for API

---

Although the admin side are written as a Single Page Application with Angular, we chose cookies for authentication, for simplicity.

Recently we have support a very simple token authenticatio so that you can call APIs add products, categories,...

### To get the access token

Send POST request to /api/token/create

```json
{
    "Username" : "<email>",
    "Password": "<password>"
}
```
Then include the returned token on every API request

Authorization : Bearer \<returned token>

### Refresh token

You can optionally include the refresh token by adding a query string `/api/token/create?includeRefreshToken=true`.

Then you can renew the access token by sending POST request to api/token/refresh

```json
{
    "token": "<returned token>",
    "refreshToken": "<returned refresh token>"
}
```

The refresh token are store in Core_User table, RefreshTokenHash column
