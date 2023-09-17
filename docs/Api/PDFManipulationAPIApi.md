# OpenAPI\Client\PDFManipulationAPIApi

All URIs are relative to https://rest.apitemplate.io, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**mergePdfs()**](PDFManipulationAPIApi.md#mergePdfs) | **POST** /v2/merge-pdfs | Join/Merge multiple PDFs |


## `mergePdfs()`

```php
mergePdfs($merge_pdfs_request, $postaction_s3_filekey, $postaction_s3_bucket, $meta): \OpenAPI\Client\Model\ResponseSuccessSingleFile
```

Join/Merge multiple PDFs

This endpoint merges/joins multiple PDF URLs into a single PDF file

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-KEY', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\PDFManipulationAPIApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$merge_pdfs_request = new \OpenAPI\Client\Model\MergePdfsRequest(); // \OpenAPI\Client\Model\MergePdfsRequest
$postaction_s3_filekey = 'postaction_s3_filekey_example'; // string | - This is to specify the file name for `Post Action(S3 Storage)`. - Please do not specify the file extension - Please make sure the file name is unique - You might use slash (/) as the folder delimiter
$postaction_s3_bucket = 'postaction_s3_bucket_example'; // string | - This is to overwrite the AWS Bucket for `Post Action(S3 Storage)`.
$meta = inv-iwj343jospig; // string | - Specify an external reference ID for your own reference. It appears in the `list-objects` API.

try {
    $result = $apiInstance->mergePdfs($merge_pdfs_request, $postaction_s3_filekey, $postaction_s3_bucket, $meta);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PDFManipulationAPIApi->mergePdfs: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **merge_pdfs_request** | [**\OpenAPI\Client\Model\MergePdfsRequest**](../Model/MergePdfsRequest.md)|  | |
| **postaction_s3_filekey** | **string**| - This is to specify the file name for &#x60;Post Action(S3 Storage)&#x60;. - Please do not specify the file extension - Please make sure the file name is unique - You might use slash (/) as the folder delimiter | [optional] |
| **postaction_s3_bucket** | **string**| - This is to overwrite the AWS Bucket for &#x60;Post Action(S3 Storage)&#x60;. | [optional] |
| **meta** | **string**| - Specify an external reference ID for your own reference. It appears in the &#x60;list-objects&#x60; API. | [optional] |

### Return type

[**\OpenAPI\Client\Model\ResponseSuccessSingleFile**](../Model/ResponseSuccessSingleFile.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
