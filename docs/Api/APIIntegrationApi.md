# OpenAPI\Client\APIIntegrationApi

All URIs are relative to https://rest.apitemplate.io, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createImage()**](APIIntegrationApi.md#createImage) | **POST** /v2/create-image | Create an Image |
| [**createPdf()**](APIIntegrationApi.md#createPdf) | **POST** /v2/create-pdf | Create a PDF |
| [**createPdfFromHtml()**](APIIntegrationApi.md#createPdfFromHtml) | **POST** /v2/create-pdf-from-html | Create a PDF from HTML |
| [**createPdfFromUrl()**](APIIntegrationApi.md#createPdfFromUrl) | **POST** /v2/create-pdf-from-url | Create a PDF from URL |
| [**deleteObject()**](APIIntegrationApi.md#deleteObject) | **GET** /v2/delete-object | Delete an Object |
| [**listObjects()**](APIIntegrationApi.md#listObjects) | **GET** /v2/list-objects | List Generated Objects |


## `createImage()`

```php
createImage($template_id, $body, $output_image_type, $expiration, $cloud_storage, $postaction_s3_filekey, $postaction_s3_bucket, $meta): \OpenAPI\Client\Model\ResponseSuccessImageFile
```

Create an Image

This endpoint creates a JPEG file(along with PNG) with JSON data and your template

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-KEY', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\APIIntegrationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$template_id = 00377b2b1e0ee394; // string | Your template id, it can be obtained in the web console
$body = array('key' => new \stdClass); // object
$output_image_type = 1; // string | - Output image type(JPEG or PNG format), default to `all`. Options are `all`, `jpegOnly`,`pngOnly`.
$expiration = 5; // int | - Expiration of the generated PDF in minutes(default to `0`, store permanently)   - Use `0` to store on cdn permanently   - Or use the range between `1` minute and `10080` minutes(7 days) to specify the expiration of the generated PDF
$cloud_storage = 1; // int | - Upload the generated PDFs/images to our storage CDN, default to `1`. If you have configured `Post Action` to upload the PDFs/Images to your own S3, please set it to `0`.
$postaction_s3_filekey = 'postaction_s3_filekey_example'; // string | - This is to specify the file name for `Post Action(S3 Storage)`. - Please do not specify the file extension - Please make sure the file name is unique - You might use slash (/) as the folder delimiter
$postaction_s3_bucket = 'postaction_s3_bucket_example'; // string | - This is to overwrite the AWS Bucket for `Post Action(S3 Storage)`.
$meta = inv-iwj343jospig; // string | - Specify an external reference ID for your own reference. It appears in the `list-objects` API.

try {
    $result = $apiInstance->createImage($template_id, $body, $output_image_type, $expiration, $cloud_storage, $postaction_s3_filekey, $postaction_s3_bucket, $meta);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling APIIntegrationApi->createImage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **template_id** | **string**| Your template id, it can be obtained in the web console | |
| **body** | **object**|  | |
| **output_image_type** | **string**| - Output image type(JPEG or PNG format), default to &#x60;all&#x60;. Options are &#x60;all&#x60;, &#x60;jpegOnly&#x60;,&#x60;pngOnly&#x60;. | [optional] |
| **expiration** | **int**| - Expiration of the generated PDF in minutes(default to &#x60;0&#x60;, store permanently)   - Use &#x60;0&#x60; to store on cdn permanently   - Or use the range between &#x60;1&#x60; minute and &#x60;10080&#x60; minutes(7 days) to specify the expiration of the generated PDF | [optional] |
| **cloud_storage** | **int**| - Upload the generated PDFs/images to our storage CDN, default to &#x60;1&#x60;. If you have configured &#x60;Post Action&#x60; to upload the PDFs/Images to your own S3, please set it to &#x60;0&#x60;. | [optional] |
| **postaction_s3_filekey** | **string**| - This is to specify the file name for &#x60;Post Action(S3 Storage)&#x60;. - Please do not specify the file extension - Please make sure the file name is unique - You might use slash (/) as the folder delimiter | [optional] |
| **postaction_s3_bucket** | **string**| - This is to overwrite the AWS Bucket for &#x60;Post Action(S3 Storage)&#x60;. | [optional] |
| **meta** | **string**| - Specify an external reference ID for your own reference. It appears in the &#x60;list-objects&#x60; API. | [optional] |

### Return type

[**\OpenAPI\Client\Model\ResponseSuccessImageFile**](../Model/ResponseSuccessImageFile.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createPdf()`

```php
createPdf($template_id, $body, $export_type, $expiration, $output_html, $output_format, $filename, $image_resample_res, $is_cmyk, $cloud_storage, $pdf_standard, $postaction_s3_filekey, $postaction_s3_bucket, $meta, $async, $webhook_url): \OpenAPI\Client\Model\ResponseSuccessPDFFile
```

Create a PDF

This endpoint creates a PDF file with JSON data and your template. We support synchoronus and asynchronous PDF generation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-KEY', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\APIIntegrationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$template_id = 00377b2b1e0ee394; // string | Your template id, it can be obtained in the web console
$body = array('key' => new \stdClass); // object
$export_type = json; // string | - Either `file` or `json`(Default).   - The option `json` returns a JSON object, and the output PDF is stored on a CDN. Use this with the parameter `expiration`   - The option `file` returns binary data of the generated PDF(Secure and completely private) and the response HTTP header Content-Disposition is set to attachment.
$expiration = 5; // int | - Expiration of the generated PDF in minutes(default to `0`, store permanently)   - Use `0` to store on cdn permanently   - Or use the range between `1` minute and `10080` minutes(7 days) to specify the expiration of the generated PDF
$output_html = 0; // string | - Either `1` or `0`(Default). - To enable output of html content, set the value to `1` and it will return in the JSON response as html_url field (as a URL)
$output_format = pdf; // string | - Either `pdf`(Default) or `html`. - It's generating PDF by default. However, you can specify output_format=html to generate only HTML(It will return in the JSON response as download_url field as a URL).
$filename = invoice_89326.pdf; // string | - Default to UUID (e.g 0c93bd9e-9ebb-4634-a70f-de9131848416.pdf). Use this to specify custom file name, it should end with `.pdf`
$image_resample_res = 150; // string | - We embed the original images by default, meaning large PDF file sizes. Specifying the option 'image_resample_res' helps reduce the PDF file size by downsampling the images of the current PDF to a resolution(in DPI). Common values are 72, 96, 150, 300 and 600.
$is_cmyk = 0; // string | - Use CMYK color profile, 1=true, 0=false. Default to '0'
$cloud_storage = 1; // int | - Upload the generated PDFs/images to our storage CDN, default to `1`. If you have configured `Post Action` to upload the PDFs/Images to your own S3, please set it to `0`.
$pdf_standard = 'pdf_standard_example'; // string | Default to PDF1.4. Options are PDFA1B, PDFA2 and PDFA3 (This is an experimental feature)
$postaction_s3_filekey = 'postaction_s3_filekey_example'; // string | - This is to specify the file name for `Post Action(S3 Storage)`. - Please do not specify the file extension - Please make sure the file name is unique - You might use slash (/) as the folder delimiter
$postaction_s3_bucket = 'postaction_s3_bucket_example'; // string | - This is to overwrite the AWS Bucket for `Post Action(S3 Storage)`.
$meta = inv-iwj343jospig; // string | - Specify an external reference ID for your own reference. It appears in the `list-objects` API.
$async = 0; // string | - Either `1` or `0`(Default).  `0` is synchronous call(default), `1` is asynchronous call - To generate PDF asynchronously, set the value to `1` and the API call returns immediately. Once the PDF document is generated, we will make a HTTP/HTTPS GET to your URL(webhook_url) and will retry for 3 times before giving up. - If `async` is set to `1`, then `webhook_url` is mandatory
$webhook_url = https://yourwebserver.com; // string | - It is the URL of your webhook URL, it starts with http:// or https:// and has to be urlencoded. - If `async` is set to `1`, then you have to specify the `webhook_url`.   #### Format of Webhook callback  Once the PDF is generated, we will initiate a HTTP/HTTPS GET call to the following URL:  https://`[yourwebserver.com]`?&primary_url=`[primary_url]`&transaction_ref=`[transaction_ref]`&status=`[status]`&message=`[message]`  - `[yourwebserver.com]`: The web services to handle the callback, which is the `webhook_url` - `[primary_url]`: The URL to the PDF document - `[transaction_ref]`: The transaction reference number - `[status]` : Status of the transaction, either `success` or `error` - `[message]` : Status message  ***The following is a sample webhook call back to your server***  https://yourwebserver.com?&primary_url=https%3A%2F%2Fpub-cdn.apitemplate.io%2F2021%2F06%2Fb692183d-46d7-3213-891a-460a5814ad3f.pdf&transaction_ref=b692183d-46d7-3213-891a-460a5814ad3f&status=success

try {
    $result = $apiInstance->createPdf($template_id, $body, $export_type, $expiration, $output_html, $output_format, $filename, $image_resample_res, $is_cmyk, $cloud_storage, $pdf_standard, $postaction_s3_filekey, $postaction_s3_bucket, $meta, $async, $webhook_url);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling APIIntegrationApi->createPdf: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **template_id** | **string**| Your template id, it can be obtained in the web console | |
| **body** | **object**|  | |
| **export_type** | **string**| - Either &#x60;file&#x60; or &#x60;json&#x60;(Default).   - The option &#x60;json&#x60; returns a JSON object, and the output PDF is stored on a CDN. Use this with the parameter &#x60;expiration&#x60;   - The option &#x60;file&#x60; returns binary data of the generated PDF(Secure and completely private) and the response HTTP header Content-Disposition is set to attachment. | [optional] |
| **expiration** | **int**| - Expiration of the generated PDF in minutes(default to &#x60;0&#x60;, store permanently)   - Use &#x60;0&#x60; to store on cdn permanently   - Or use the range between &#x60;1&#x60; minute and &#x60;10080&#x60; minutes(7 days) to specify the expiration of the generated PDF | [optional] |
| **output_html** | **string**| - Either &#x60;1&#x60; or &#x60;0&#x60;(Default). - To enable output of html content, set the value to &#x60;1&#x60; and it will return in the JSON response as html_url field (as a URL) | [optional] |
| **output_format** | **string**| - Either &#x60;pdf&#x60;(Default) or &#x60;html&#x60;. - It&#39;s generating PDF by default. However, you can specify output_format&#x3D;html to generate only HTML(It will return in the JSON response as download_url field as a URL). | [optional] |
| **filename** | **string**| - Default to UUID (e.g 0c93bd9e-9ebb-4634-a70f-de9131848416.pdf). Use this to specify custom file name, it should end with &#x60;.pdf&#x60; | [optional] |
| **image_resample_res** | **string**| - We embed the original images by default, meaning large PDF file sizes. Specifying the option &#39;image_resample_res&#39; helps reduce the PDF file size by downsampling the images of the current PDF to a resolution(in DPI). Common values are 72, 96, 150, 300 and 600. | [optional] |
| **is_cmyk** | **string**| - Use CMYK color profile, 1&#x3D;true, 0&#x3D;false. Default to &#39;0&#39; | [optional] |
| **cloud_storage** | **int**| - Upload the generated PDFs/images to our storage CDN, default to &#x60;1&#x60;. If you have configured &#x60;Post Action&#x60; to upload the PDFs/Images to your own S3, please set it to &#x60;0&#x60;. | [optional] |
| **pdf_standard** | **string**| Default to PDF1.4. Options are PDFA1B, PDFA2 and PDFA3 (This is an experimental feature) | [optional] |
| **postaction_s3_filekey** | **string**| - This is to specify the file name for &#x60;Post Action(S3 Storage)&#x60;. - Please do not specify the file extension - Please make sure the file name is unique - You might use slash (/) as the folder delimiter | [optional] |
| **postaction_s3_bucket** | **string**| - This is to overwrite the AWS Bucket for &#x60;Post Action(S3 Storage)&#x60;. | [optional] |
| **meta** | **string**| - Specify an external reference ID for your own reference. It appears in the &#x60;list-objects&#x60; API. | [optional] |
| **async** | **string**| - Either &#x60;1&#x60; or &#x60;0&#x60;(Default).  &#x60;0&#x60; is synchronous call(default), &#x60;1&#x60; is asynchronous call - To generate PDF asynchronously, set the value to &#x60;1&#x60; and the API call returns immediately. Once the PDF document is generated, we will make a HTTP/HTTPS GET to your URL(webhook_url) and will retry for 3 times before giving up. - If &#x60;async&#x60; is set to &#x60;1&#x60;, then &#x60;webhook_url&#x60; is mandatory | [optional] |
| **webhook_url** | **string**| - It is the URL of your webhook URL, it starts with http:// or https:// and has to be urlencoded. - If &#x60;async&#x60; is set to &#x60;1&#x60;, then you have to specify the &#x60;webhook_url&#x60;.   #### Format of Webhook callback  Once the PDF is generated, we will initiate a HTTP/HTTPS GET call to the following URL:  https://&#x60;[yourwebserver.com]&#x60;?&amp;primary_url&#x3D;&#x60;[primary_url]&#x60;&amp;transaction_ref&#x3D;&#x60;[transaction_ref]&#x60;&amp;status&#x3D;&#x60;[status]&#x60;&amp;message&#x3D;&#x60;[message]&#x60;  - &#x60;[yourwebserver.com]&#x60;: The web services to handle the callback, which is the &#x60;webhook_url&#x60; - &#x60;[primary_url]&#x60;: The URL to the PDF document - &#x60;[transaction_ref]&#x60;: The transaction reference number - &#x60;[status]&#x60; : Status of the transaction, either &#x60;success&#x60; or &#x60;error&#x60; - &#x60;[message]&#x60; : Status message  ***The following is a sample webhook call back to your server***  https://yourwebserver.com?&amp;primary_url&#x3D;https%3A%2F%2Fpub-cdn.apitemplate.io%2F2021%2F06%2Fb692183d-46d7-3213-891a-460a5814ad3f.pdf&amp;transaction_ref&#x3D;b692183d-46d7-3213-891a-460a5814ad3f&amp;status&#x3D;success | [optional] |

### Return type

[**\OpenAPI\Client\Model\ResponseSuccessPDFFile**](../Model/ResponseSuccessPDFFile.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createPdfFromHtml()`

```php
createPdfFromHtml($create_pdf_from_html_request, $export_type, $expiration, $output_format, $filename, $image_resample_res, $is_cmyk, $cloud_storage, $pdf_standard, $postaction_s3_filekey, $postaction_s3_bucket, $meta, $async, $webhook_url): \OpenAPI\Client\Model\ResponseSuccessPDFFile
```

Create a PDF from HTML

- This endpoint creates a PDF file from HTML with JSON data

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-KEY', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\APIIntegrationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_pdf_from_html_request = new \OpenAPI\Client\Model\CreatePdfFromHtmlRequest(); // \OpenAPI\Client\Model\CreatePdfFromHtmlRequest
$export_type = json; // string | - Either `file` or `json`(Default).   - The option `json` returns a JSON object, and the output PDF is stored on a CDN. Use this with the parameter `expiration`   - The option `file` returns binary data of the generated PDF(Secure and completely private) and the response HTTP header Content-Disposition is set to attachment.
$expiration = 5; // int | - Expiration of the generated PDF in minutes(default to `0`, store permanently)   - Use `0` to store on cdn permanently   - Or use the range between `1` minute and `10080` minutes(7 days) to specify the expiration of the generated PDF
$output_format = pdf; // string | - Either `pdf`(Default) or `html`. - It's generating PDF by default. However, you can specify output_format=html to generate only HTML(It will return in the JSON response as download_url field as a URL).
$filename = invoice_89326.pdf; // string | - Default to UUID (e.g 0c93bd9e-9ebb-4634-a70f-de9131848416.pdf). Use this to specify custom file name, it should end with `.pdf`
$image_resample_res = 150; // string | - We embed the original images by default, meaning large PDF file sizes. Specifying the option 'image_resample_res' helps reduce the PDF file size by downsampling the images of the current PDF to a resolution(in DPI). Common values are 72, 96, 150, 300 and 600.
$is_cmyk = 0; // string | - Use CMYK color profile, 1=true, 0=false. Default to '0'
$cloud_storage = 1; // int | - Upload the generated PDFs/images to our storage CDN, default to `1`. If you have configured `Post Action` to upload the PDFs/Images to your own S3, please set it to `0`.
$pdf_standard = 'pdf_standard_example'; // string | Default to PDF1.4. Options are PDFA1B, PDFA2 and PDFA3 (This is an experimental feature)
$postaction_s3_filekey = 'postaction_s3_filekey_example'; // string | - This is to specify the file name for `Post Action(S3 Storage)`. - Please do not specify the file extension - Please make sure the file name is unique - You might use slash (/) as the folder delimiter
$postaction_s3_bucket = 'postaction_s3_bucket_example'; // string | - This is to overwrite the AWS Bucket for `Post Action(S3 Storage)`.
$meta = inv-iwj343jospig; // string | - Specify an external reference ID for your own reference. It appears in the `list-objects` API.
$async = 0; // string | - Either `1` or `0`(Default).  `0` is synchronous call(default), `1` is asynchronous call - To generate PDF asynchronously, set the value to `1` and the API call returns immediately. Once the PDF document is generated, we will make a HTTP/HTTPS GET to your URL(webhook_url) and will retry for 3 times before giving up. - If `async` is set to `1`, then `webhook_url` is mandatory
$webhook_url = https://yourwebserver.com; // string | - It is the URL of your webhook URL, it starts with http:// or https:// and has to be urlencoded. - If `async` is set to `1`, then you have to specify the `webhook_url`.   #### Format of Webhook callback  Once the PDF is generated, we will initiate a HTTP/HTTPS GET call to the following URL:  https://`[yourwebserver.com]`?&primary_url=`[primary_url]`&transaction_ref=`[transaction_ref]`&status=`[status]`&message=`[message]`  - `[yourwebserver.com]`: The web services to handle the callback, which is the `webhook_url` - `[primary_url]`: The URL to the PDF document - `[transaction_ref]`: The transaction reference number - `[status]` : Status of the transaction, either `success` or `error` - `[message]` : Status message  ***The following is a sample webhook call back to your server***  https://yourwebserver.com?&primary_url=https%3A%2F%2Fpub-cdn.apitemplate.io%2F2021%2F06%2Fb692183d-46d7-3213-891a-460a5814ad3f.pdf&transaction_ref=b692183d-46d7-3213-891a-460a5814ad3f&status=success

try {
    $result = $apiInstance->createPdfFromHtml($create_pdf_from_html_request, $export_type, $expiration, $output_format, $filename, $image_resample_res, $is_cmyk, $cloud_storage, $pdf_standard, $postaction_s3_filekey, $postaction_s3_bucket, $meta, $async, $webhook_url);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling APIIntegrationApi->createPdfFromHtml: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_pdf_from_html_request** | [**\OpenAPI\Client\Model\CreatePdfFromHtmlRequest**](../Model/CreatePdfFromHtmlRequest.md)|  | |
| **export_type** | **string**| - Either &#x60;file&#x60; or &#x60;json&#x60;(Default).   - The option &#x60;json&#x60; returns a JSON object, and the output PDF is stored on a CDN. Use this with the parameter &#x60;expiration&#x60;   - The option &#x60;file&#x60; returns binary data of the generated PDF(Secure and completely private) and the response HTTP header Content-Disposition is set to attachment. | [optional] |
| **expiration** | **int**| - Expiration of the generated PDF in minutes(default to &#x60;0&#x60;, store permanently)   - Use &#x60;0&#x60; to store on cdn permanently   - Or use the range between &#x60;1&#x60; minute and &#x60;10080&#x60; minutes(7 days) to specify the expiration of the generated PDF | [optional] |
| **output_format** | **string**| - Either &#x60;pdf&#x60;(Default) or &#x60;html&#x60;. - It&#39;s generating PDF by default. However, you can specify output_format&#x3D;html to generate only HTML(It will return in the JSON response as download_url field as a URL). | [optional] |
| **filename** | **string**| - Default to UUID (e.g 0c93bd9e-9ebb-4634-a70f-de9131848416.pdf). Use this to specify custom file name, it should end with &#x60;.pdf&#x60; | [optional] |
| **image_resample_res** | **string**| - We embed the original images by default, meaning large PDF file sizes. Specifying the option &#39;image_resample_res&#39; helps reduce the PDF file size by downsampling the images of the current PDF to a resolution(in DPI). Common values are 72, 96, 150, 300 and 600. | [optional] |
| **is_cmyk** | **string**| - Use CMYK color profile, 1&#x3D;true, 0&#x3D;false. Default to &#39;0&#39; | [optional] |
| **cloud_storage** | **int**| - Upload the generated PDFs/images to our storage CDN, default to &#x60;1&#x60;. If you have configured &#x60;Post Action&#x60; to upload the PDFs/Images to your own S3, please set it to &#x60;0&#x60;. | [optional] |
| **pdf_standard** | **string**| Default to PDF1.4. Options are PDFA1B, PDFA2 and PDFA3 (This is an experimental feature) | [optional] |
| **postaction_s3_filekey** | **string**| - This is to specify the file name for &#x60;Post Action(S3 Storage)&#x60;. - Please do not specify the file extension - Please make sure the file name is unique - You might use slash (/) as the folder delimiter | [optional] |
| **postaction_s3_bucket** | **string**| - This is to overwrite the AWS Bucket for &#x60;Post Action(S3 Storage)&#x60;. | [optional] |
| **meta** | **string**| - Specify an external reference ID for your own reference. It appears in the &#x60;list-objects&#x60; API. | [optional] |
| **async** | **string**| - Either &#x60;1&#x60; or &#x60;0&#x60;(Default).  &#x60;0&#x60; is synchronous call(default), &#x60;1&#x60; is asynchronous call - To generate PDF asynchronously, set the value to &#x60;1&#x60; and the API call returns immediately. Once the PDF document is generated, we will make a HTTP/HTTPS GET to your URL(webhook_url) and will retry for 3 times before giving up. - If &#x60;async&#x60; is set to &#x60;1&#x60;, then &#x60;webhook_url&#x60; is mandatory | [optional] |
| **webhook_url** | **string**| - It is the URL of your webhook URL, it starts with http:// or https:// and has to be urlencoded. - If &#x60;async&#x60; is set to &#x60;1&#x60;, then you have to specify the &#x60;webhook_url&#x60;.   #### Format of Webhook callback  Once the PDF is generated, we will initiate a HTTP/HTTPS GET call to the following URL:  https://&#x60;[yourwebserver.com]&#x60;?&amp;primary_url&#x3D;&#x60;[primary_url]&#x60;&amp;transaction_ref&#x3D;&#x60;[transaction_ref]&#x60;&amp;status&#x3D;&#x60;[status]&#x60;&amp;message&#x3D;&#x60;[message]&#x60;  - &#x60;[yourwebserver.com]&#x60;: The web services to handle the callback, which is the &#x60;webhook_url&#x60; - &#x60;[primary_url]&#x60;: The URL to the PDF document - &#x60;[transaction_ref]&#x60;: The transaction reference number - &#x60;[status]&#x60; : Status of the transaction, either &#x60;success&#x60; or &#x60;error&#x60; - &#x60;[message]&#x60; : Status message  ***The following is a sample webhook call back to your server***  https://yourwebserver.com?&amp;primary_url&#x3D;https%3A%2F%2Fpub-cdn.apitemplate.io%2F2021%2F06%2Fb692183d-46d7-3213-891a-460a5814ad3f.pdf&amp;transaction_ref&#x3D;b692183d-46d7-3213-891a-460a5814ad3f&amp;status&#x3D;success | [optional] |

### Return type

[**\OpenAPI\Client\Model\ResponseSuccessPDFFile**](../Model/ResponseSuccessPDFFile.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createPdfFromUrl()`

```php
createPdfFromUrl($create_pdf_from_url_request, $export_type, $expiration, $output_format, $filename, $image_resample_res, $is_cmyk, $cloud_storage, $pdf_standard, $postaction_s3_filekey, $postaction_s3_bucket, $meta, $async, $webhook_url): \OpenAPI\Client\Model\ResponseSuccessPDFFile
```

Create a PDF from URL

- This endpoint creates a PDF file from a URL

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-KEY', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\APIIntegrationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_pdf_from_url_request = new \OpenAPI\Client\Model\CreatePdfFromUrlRequest(); // \OpenAPI\Client\Model\CreatePdfFromUrlRequest
$export_type = json; // string | - Either `file` or `json`(Default).   - The option `json` returns a JSON object, and the output PDF is stored on a CDN. Use this with the parameter `expiration`   - The option `file` returns binary data of the generated PDF(Secure and completely private) and the response HTTP header Content-Disposition is set to attachment.
$expiration = 5; // int | - Expiration of the generated PDF in minutes(default to `0`, store permanently)   - Use `0` to store on cdn permanently   - Or use the range between `1` minute and `10080` minutes(7 days) to specify the expiration of the generated PDF
$output_format = pdf; // string | - Either `pdf`(Default) or `html`. - It's generating PDF by default. However, you can specify output_format=html to generate only HTML(It will return in the JSON response as download_url field as a URL).
$filename = invoice_89326.pdf; // string | - Default to UUID (e.g 0c93bd9e-9ebb-4634-a70f-de9131848416.pdf). Use this to specify custom file name, it should end with `.pdf`
$image_resample_res = 150; // string | - We embed the original images by default, meaning large PDF file sizes. Specifying the option 'image_resample_res' helps reduce the PDF file size by downsampling the images of the current PDF to a resolution(in DPI). Common values are 72, 96, 150, 300 and 600.
$is_cmyk = 0; // string | - Use CMYK color profile, 1=true, 0=false. Default to '0'
$cloud_storage = 1; // int | - Upload the generated PDFs/images to our storage CDN, default to `1`. If you have configured `Post Action` to upload the PDFs/Images to your own S3, please set it to `0`.
$pdf_standard = 'pdf_standard_example'; // string | Default to PDF1.4. Options are PDFA1B, PDFA2 and PDFA3 (This is an experimental feature)
$postaction_s3_filekey = 'postaction_s3_filekey_example'; // string | - This is to specify the file name for `Post Action(S3 Storage)`. - Please do not specify the file extension - Please make sure the file name is unique - You might use slash (/) as the folder delimiter
$postaction_s3_bucket = 'postaction_s3_bucket_example'; // string | - This is to overwrite the AWS Bucket for `Post Action(S3 Storage)`.
$meta = inv-iwj343jospig; // string | - Specify an external reference ID for your own reference. It appears in the `list-objects` API.
$async = 0; // string | - Either `1` or `0`(Default).  `0` is synchronous call(default), `1` is asynchronous call - To generate PDF asynchronously, set the value to `1` and the API call returns immediately. Once the PDF document is generated, we will make a HTTP/HTTPS GET to your URL(webhook_url) and will retry for 3 times before giving up. - If `async` is set to `1`, then `webhook_url` is mandatory
$webhook_url = https://yourwebserver.com; // string | - It is the URL of your webhook URL, it starts with http:// or https:// and has to be urlencoded. - If `async` is set to `1`, then you have to specify the `webhook_url`.   #### Format of Webhook callback  Once the PDF is generated, we will initiate a HTTP/HTTPS GET call to the following URL:  https://`[yourwebserver.com]`?&primary_url=`[primary_url]`&transaction_ref=`[transaction_ref]`&status=`[status]`&message=`[message]`  - `[yourwebserver.com]`: The web services to handle the callback, which is the `webhook_url` - `[primary_url]`: The URL to the PDF document - `[transaction_ref]`: The transaction reference number - `[status]` : Status of the transaction, either `success` or `error` - `[message]` : Status message  ***The following is a sample webhook call back to your server***  https://yourwebserver.com?&primary_url=https%3A%2F%2Fpub-cdn.apitemplate.io%2F2021%2F06%2Fb692183d-46d7-3213-891a-460a5814ad3f.pdf&transaction_ref=b692183d-46d7-3213-891a-460a5814ad3f&status=success

try {
    $result = $apiInstance->createPdfFromUrl($create_pdf_from_url_request, $export_type, $expiration, $output_format, $filename, $image_resample_res, $is_cmyk, $cloud_storage, $pdf_standard, $postaction_s3_filekey, $postaction_s3_bucket, $meta, $async, $webhook_url);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling APIIntegrationApi->createPdfFromUrl: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_pdf_from_url_request** | [**\OpenAPI\Client\Model\CreatePdfFromUrlRequest**](../Model/CreatePdfFromUrlRequest.md)|  | |
| **export_type** | **string**| - Either &#x60;file&#x60; or &#x60;json&#x60;(Default).   - The option &#x60;json&#x60; returns a JSON object, and the output PDF is stored on a CDN. Use this with the parameter &#x60;expiration&#x60;   - The option &#x60;file&#x60; returns binary data of the generated PDF(Secure and completely private) and the response HTTP header Content-Disposition is set to attachment. | [optional] |
| **expiration** | **int**| - Expiration of the generated PDF in minutes(default to &#x60;0&#x60;, store permanently)   - Use &#x60;0&#x60; to store on cdn permanently   - Or use the range between &#x60;1&#x60; minute and &#x60;10080&#x60; minutes(7 days) to specify the expiration of the generated PDF | [optional] |
| **output_format** | **string**| - Either &#x60;pdf&#x60;(Default) or &#x60;html&#x60;. - It&#39;s generating PDF by default. However, you can specify output_format&#x3D;html to generate only HTML(It will return in the JSON response as download_url field as a URL). | [optional] |
| **filename** | **string**| - Default to UUID (e.g 0c93bd9e-9ebb-4634-a70f-de9131848416.pdf). Use this to specify custom file name, it should end with &#x60;.pdf&#x60; | [optional] |
| **image_resample_res** | **string**| - We embed the original images by default, meaning large PDF file sizes. Specifying the option &#39;image_resample_res&#39; helps reduce the PDF file size by downsampling the images of the current PDF to a resolution(in DPI). Common values are 72, 96, 150, 300 and 600. | [optional] |
| **is_cmyk** | **string**| - Use CMYK color profile, 1&#x3D;true, 0&#x3D;false. Default to &#39;0&#39; | [optional] |
| **cloud_storage** | **int**| - Upload the generated PDFs/images to our storage CDN, default to &#x60;1&#x60;. If you have configured &#x60;Post Action&#x60; to upload the PDFs/Images to your own S3, please set it to &#x60;0&#x60;. | [optional] |
| **pdf_standard** | **string**| Default to PDF1.4. Options are PDFA1B, PDFA2 and PDFA3 (This is an experimental feature) | [optional] |
| **postaction_s3_filekey** | **string**| - This is to specify the file name for &#x60;Post Action(S3 Storage)&#x60;. - Please do not specify the file extension - Please make sure the file name is unique - You might use slash (/) as the folder delimiter | [optional] |
| **postaction_s3_bucket** | **string**| - This is to overwrite the AWS Bucket for &#x60;Post Action(S3 Storage)&#x60;. | [optional] |
| **meta** | **string**| - Specify an external reference ID for your own reference. It appears in the &#x60;list-objects&#x60; API. | [optional] |
| **async** | **string**| - Either &#x60;1&#x60; or &#x60;0&#x60;(Default).  &#x60;0&#x60; is synchronous call(default), &#x60;1&#x60; is asynchronous call - To generate PDF asynchronously, set the value to &#x60;1&#x60; and the API call returns immediately. Once the PDF document is generated, we will make a HTTP/HTTPS GET to your URL(webhook_url) and will retry for 3 times before giving up. - If &#x60;async&#x60; is set to &#x60;1&#x60;, then &#x60;webhook_url&#x60; is mandatory | [optional] |
| **webhook_url** | **string**| - It is the URL of your webhook URL, it starts with http:// or https:// and has to be urlencoded. - If &#x60;async&#x60; is set to &#x60;1&#x60;, then you have to specify the &#x60;webhook_url&#x60;.   #### Format of Webhook callback  Once the PDF is generated, we will initiate a HTTP/HTTPS GET call to the following URL:  https://&#x60;[yourwebserver.com]&#x60;?&amp;primary_url&#x3D;&#x60;[primary_url]&#x60;&amp;transaction_ref&#x3D;&#x60;[transaction_ref]&#x60;&amp;status&#x3D;&#x60;[status]&#x60;&amp;message&#x3D;&#x60;[message]&#x60;  - &#x60;[yourwebserver.com]&#x60;: The web services to handle the callback, which is the &#x60;webhook_url&#x60; - &#x60;[primary_url]&#x60;: The URL to the PDF document - &#x60;[transaction_ref]&#x60;: The transaction reference number - &#x60;[status]&#x60; : Status of the transaction, either &#x60;success&#x60; or &#x60;error&#x60; - &#x60;[message]&#x60; : Status message  ***The following is a sample webhook call back to your server***  https://yourwebserver.com?&amp;primary_url&#x3D;https%3A%2F%2Fpub-cdn.apitemplate.io%2F2021%2F06%2Fb692183d-46d7-3213-891a-460a5814ad3f.pdf&amp;transaction_ref&#x3D;b692183d-46d7-3213-891a-460a5814ad3f&amp;status&#x3D;success | [optional] |

### Return type

[**\OpenAPI\Client\Model\ResponseSuccessPDFFile**](../Model/ResponseSuccessPDFFile.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteObject()`

```php
deleteObject($transaction_ref): \OpenAPI\Client\Model\ResponseSuccessDeleteObject
```

Delete an Object

Delete a PDF or an image from CDN and mark the transaction as deleted

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-KEY', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\APIIntegrationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$transaction_ref = 1618d386-2343-3d234-b9c7-99c82bb9f104; // string | Object transaction reference

try {
    $result = $apiInstance->deleteObject($transaction_ref);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling APIIntegrationApi->deleteObject: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **transaction_ref** | **string**| Object transaction reference | |

### Return type

[**\OpenAPI\Client\Model\ResponseSuccessDeleteObject**](../Model/ResponseSuccessDeleteObject.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listObjects()`

```php
listObjects($limit, $offset, $template_id, $transaction_type): \OpenAPI\Client\Model\ResponseSuccessListObjects
```

List Generated Objects

Retrieves all the generated PDFs and images

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-KEY', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\APIIntegrationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$limit = 300; // string | Retrieve only the number of records specified. Default to 300
$offset = 0; // string | Offset is used to skip the number of records from the results. Default to 0
$template_id = 00377b2b1e0ee394; // string | Filtered by template id
$transaction_type = MERGE; // string | Filtered by transaction type, options are `PDF`, `JPEG` or `MERGE`

try {
    $result = $apiInstance->listObjects($limit, $offset, $template_id, $transaction_type);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling APIIntegrationApi->listObjects: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **limit** | **string**| Retrieve only the number of records specified. Default to 300 | [optional] |
| **offset** | **string**| Offset is used to skip the number of records from the results. Default to 0 | [optional] |
| **template_id** | **string**| Filtered by template id | [optional] |
| **transaction_type** | **string**| Filtered by transaction type, options are &#x60;PDF&#x60;, &#x60;JPEG&#x60; or &#x60;MERGE&#x60; | [optional] |

### Return type

[**\OpenAPI\Client\Model\ResponseSuccessListObjects**](../Model/ResponseSuccessListObjects.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
