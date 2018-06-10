# Development tips

---

Any changes that you have made in modules need to be copied to the WebHost to be loaded. You can do this in several ways:

- Build SimplCommerce.WebHost which will trigger the "copy-modules" gulp task
- Manually run the "copy-modules" gulp task in the Task Runner Explorer
- If your changes are only static content like: .css, .js, .cshtml you can simply run the "copy-static" and then refresh the browser.

![Task runner](images/taskrunner.png)

The gulp file can be found at https://github.com/simplcommerce/SimplCommerce/blob/master/src/SimplCommerce.WebHost/gulpfile.js
