# # CreatePdfFromHtmlRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**body** | **string** | The HTML body content for the PDF. This property supports HTML markup and can include Jinja2 syntax (e.g {{name}}). The value of {{name}} will be replaced with the actual value provided in the data object. | [optional]
**css** | **string** | The CSS styles to be applied to the PDF. This property should contain valid CSS markup and should also include the style tag. | [optional]
**data** | **object** | The data object containing values for dynamic content in the HTML body. This object should include properties with corresponding values. | [optional]
**settings** | [**\OpenAPI\Client\Model\PDFGenerationSettingsObject**](PDFGenerationSettingsObject.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
