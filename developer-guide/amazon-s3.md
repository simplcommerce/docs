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
      "RegionEndpointName": "<Region name>",
      "AccessKeyId": "<Your access key>",
      "SecretAccessKey": "<Your secret key>",
      "BucketName": "<Your bucket name>",
      "PublicEndpoint" <Optional >
    }
  }
```

Then update the these configuration values according to your aws settings. For use in production, we recommend that the bucket should be served via CloudFront CDN. Then in that case, add your cloudfront domain to the PublicEndpoint.

Note: If you like you can add these setting to the Core_AppSettings table instead.

## Active StorageAmazonS3 module

By default, simplcommerce using StorageLocal module and store the media in the local folder SimplCommerce.WebHost\wwwroot\user-content.

The current workaround is:

In the SimplCommerce.WebHost.csproj replace 

```xml
<ProjectReference Include="..\Modules\SimplCommerce.Module.StorageLocal\SimplCommerce.Module.StorageLocal.csproj" />
```

by

```xml
<ProjectReference Include="..\Modules\SimplCommerce.Module.StorageAmazonS3\SimplCommerce.Module.StorageAmazonS3.csproj" />
```

And also replace the module SimplCommerce.Module.StorageLocal to SimplCommerce.Module.StorageAmazonS3 in modules.json in the WebHost

- Build the solution then enjoy.
