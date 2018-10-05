# Some notes for exporting PDF

---

SimplCommerce use a library called [DinkToPdf](https://github.com/rdvojmoc/DinkToPdf) to export PDF from html string.  DinkToPdf is a cross-platform wrapper around the Webkit HTML to PDF library [wkhtmltopdf](https://wkhtmltopdf.org).


To make it work, you have to copy native library to root folder of the SimplCommerce.WebHost. You can find latest version of native library [here](https://github.com/rdvojmoc/DinkToPdf/tree/v1.0.8/v0.12.4). Select appropriate library for your OS (libwkhtmltox.dll for Windows, libwkhtmltox.so for Linux and libwkhtmltox.dylib for Mac) and platform (64 or 32 bit).

When published, this navive library need to be inlcuded at the root folder.

Note, When running in IIS Express, the app cannot load the libwkhtmltox. Haven't figured out why.
