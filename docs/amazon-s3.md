# How to use StorageAmazonS3 module

---

You can easily make SimplCommerce using Amazon S3 to store and serve media like product images, category images,.. 

## Prepare the bucket

Login to aws console and create a bucket.

## Add configuration.

Add the following configuration below to the appsettings.json

```json
  "AWS": {
    "S3": {
      "RegionEndpointName": "<region name>",
      "AccessKeyId": "<Your access key>",
      "SecretAccessKey": "<Your secret key>",
      "BucketName": "<Your bucket name>"
    }
  }
```

Then update the these configuration values according to your aws settings.

Note: If you like you can add these setting to the Core_AppSettings table instead.

## Active StorageAmazonS3 module

By default, simplcommerce using StorageLocal module and store the media in the local folder SimplCommerce.WebHost\wwwroot\user-content.

The current workaround is:

- Delete the module.json in the SimplCommerce.Module.StorageLocal. So that it isn't copied to the Host when build
- Create a module.json in the SimplCommerce.Module.StorageAmazonS3 with the content below.

```json
{
  "name": "storageAmazonS3",
  "fullName": "SimplCommerce.Module.StorageAmazonS3",
  "version": "1.0.0"
}
```

- Build the solution then enjoy.






