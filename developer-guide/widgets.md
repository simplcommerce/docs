# Widgets

A widget is a fragment of UI that can be easily added to predefined placeholders in the views. Currently SimpleCommerce support 3 widget zones (placeholders) all of them are in the home page. We will support more widget zone in the futures, you can also define your own zones.

## Steps to develop new widgets

1. Insert new record to [Core_Widget] table. We recommend that you should add the seed data in EF Core for it. See the example [here](https://github.com/simplcommerce/SimplCommerce/blob/f485ed52c9416ca1dd52fdef433caae94447bed7/src/Modules/SimplCommerce.Module.Cms/Data/CmsCustomModelBuilder.cs#L22)
2. Add YourWidgetNameApiController and implement Get/Post/Put, see [Carousel widget](https://github.com/simplcommerce/SimplCommerce/blob/master/src/Modules/SimplCommerce.Module.Cms/Controllers/CarouselWidgetApiController.cs) as an example. 
3. Add AngularJS code for create and edit widget. The route to the form should match to then one that you your widget record in the [Core_Widget] table
4. Create a ViewComponent to display your widget to users






