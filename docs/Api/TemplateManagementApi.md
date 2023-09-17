# OpenAPI\Client\TemplateManagementApi

All URIs are relative to https://rest.apitemplate.io, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getTemplate()**](TemplateManagementApi.md#getTemplate) | **GET** /v2/get-template | Get PDF template |
| [**listTemplates()**](TemplateManagementApi.md#listTemplates) | **GET** /v2/list-templates | List Templates |
| [**updateTemplate()**](TemplateManagementApi.md#updateTemplate) | **POST** /v2/update-template | Update PDF Template |


## `getTemplate()`

```php
getTemplate($template_id): \OpenAPI\Client\Model\ResponseSuccessTemplate
```

Get PDF template

Retrieves information of the PDF template (**This is an experimental API, contact support to learn more**)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-KEY', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\TemplateManagementApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$template_id = 00377b2b1e0ee394; // string | Your template id, it can be obtained in the web console(Manage Templates)

try {
    $result = $apiInstance->getTemplate($template_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TemplateManagementApi->getTemplate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **template_id** | **string**| Your template id, it can be obtained in the web console(Manage Templates) | [optional] |

### Return type

[**\OpenAPI\Client\Model\ResponseSuccessTemplate**](../Model/ResponseSuccessTemplate.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listTemplates()`

```php
listTemplates($limit, $offset, $format, $template_id, $group_name, $with_layer_info): \OpenAPI\Client\Model\ResponseSuccessListTemplates
```

List Templates

Retrieves the information of templates

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-KEY', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\TemplateManagementApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$limit = 300; // string | Retrieve only the number of records specified. Default to 300
$offset = 0; // string | Offset is used to skip the number of records from the results. Default to 0
$format = JPEG; // string | To filter the templates by either 'PDF' or 'JPEG'
$template_id = 00377b2b1e0ee394; // string | To filter the templates by template id
$group_name = custom; // string | To filter the templates by the group name
$with_layer_info = 0; // string | Return along with layer information for image templates, 0=false , 1=true. Default to '0'

try {
    $result = $apiInstance->listTemplates($limit, $offset, $format, $template_id, $group_name, $with_layer_info);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TemplateManagementApi->listTemplates: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **limit** | **string**| Retrieve only the number of records specified. Default to 300 | [optional] |
| **offset** | **string**| Offset is used to skip the number of records from the results. Default to 0 | [optional] |
| **format** | **string**| To filter the templates by either &#39;PDF&#39; or &#39;JPEG&#39; | [optional] |
| **template_id** | **string**| To filter the templates by template id | [optional] |
| **group_name** | **string**| To filter the templates by the group name | [optional] |
| **with_layer_info** | **string**| Return along with layer information for image templates, 0&#x3D;false , 1&#x3D;true. Default to &#39;0&#39; | [optional] |

### Return type

[**\OpenAPI\Client\Model\ResponseSuccessListTemplates**](../Model/ResponseSuccessListTemplates.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateTemplate()`

```php
updateTemplate($update_template_request): \OpenAPI\Client\Model\ResponseSuccess
```

Update PDF Template

This endpoint updates PDF template (**This is an experimental API, contact support to learn more**)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-KEY', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\TemplateManagementApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$update_template_request = new \OpenAPI\Client\Model\UpdateTemplateRequest(); // \OpenAPI\Client\Model\UpdateTemplateRequest

try {
    $result = $apiInstance->updateTemplate($update_template_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TemplateManagementApi->updateTemplate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **update_template_request** | [**\OpenAPI\Client\Model\UpdateTemplateRequest**](../Model/UpdateTemplateRequest.md)|  | |

### Return type

[**\OpenAPI\Client\Model\ResponseSuccess**](../Model/ResponseSuccess.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
