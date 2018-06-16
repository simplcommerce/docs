# Theme development

---

It is very easy to develop a new theme in SimplCommerce. You don't need to instsall any thing to develop and test your theme. All you need is download the latest release of SimplCommerce at https://github.com/simplcommerce/SimplCommerce/releases. Depend on your OS, 
pick a Windows or Mac version, extract the zip file, run the app by click on SimplCommerce.WebHost.exe (Windows), or type the './SimplCommerce.WebHost' in the Terminal and hit Enter (Mac).

Of course, you can run the full source code with .NET Core SDK for advanced debuging.

## Steps to create a new theme
- Create a folder SimplCommerce.WebHost/Themes/[YourThemeName]. The theme name should be in PascalCase, no spacing.
- Create a theme.json file in your newly created folder

```json
{
  "name": "YourThemeName",
  "fullName": "YourThemeName",
  "displayName": "Your theme name",
  "version": "1.0.0"
}
```
- In your theme folder, create Views/Shared/_Layout.cshtml, this is the layout of your theme. You can copy the existing _Layout.cshtml then modify it. You can add your custom style sheet or change the html structure.

- If you want to change the html structure of some particular views. Then following the origin views' structure, create your own views in your theme folder. It will override the original one. Not overrided views will fallback to the origin views.  Please check out the SampleTheme.

- Create a folder SimplCommerce.WebHost/wwwroot/themes/[YourThemeName], add your css, images,... there. Also add the screenshot of your view SimplCommerce.WebHost/wwwroot/themes/[YourThemeName]/[YourThemeName].png.

- Login as admin, go to System --> Themes. You will see your theme there. Click "Preview" to see how it looks like, and "Use" for others people can see it.

- When your theme looks great, you can download it from the admin, apply it on the server or publish it in the [marketplace](http://marketplace.simplcommerce.com)
