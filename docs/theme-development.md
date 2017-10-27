# Theme development

---

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
- In your theme folder, create Views/Shared/_Layout.cshtml, this is the layout of your theme. You can copied the existing _Layout.cshtml then modify it. You can add your custom style sheet or change the html structure.

- If you want to change the html structure of some particular views. Then following the origin views' structure, create your own views. The other will fallback to the origin views.  Please check out the SampleTheme. 

- Create a folder SimplCommerce.WebHost/wwwroot/themes/[YourThemeName], add your css, images,... there. Also add the screenshot of your view SimplCommerce.WebHost/wwwroot/themes/[YourThemeName]/[YourThemeName].png.

- Login as admin, go to System --> Themes. You will see your theme there. Click "Preview" to see how it looks like, and "Use" for others people can see it.

## Next

Package your theme and publish to marketplace. This feature will be available soon

