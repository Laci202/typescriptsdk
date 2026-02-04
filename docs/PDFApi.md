# PDFApi

All URIs are relative to *https://api.pdftemplateapi.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createPdf**](PDFApi.md#createpdfoperation) | **POST** /v1/pdf/create | Generate PDF from template |



## createPdf

> CreatePdfResponse createPdf(createPdfRequest)

Generate PDF from template

Generate a PDF from a saved template with dynamic data.  **Authentication:** API Key required (&#x60;x-api-key&#x60; header)  ## Request Body  | Field | Type | Required | Description | |-------|------|----------|-------------| | &#x60;template_id&#x60; | string | ✅ Yes | Template short ID (12 characters) | | &#x60;data&#x60; | object | ✅ Yes | Key-value data to render in template | | &#x60;export_type&#x60; | string | No | &#x60;url&#x60; (default) or &#x60;binary&#x60; | | &#x60;expiration&#x60; | integer | No | URL expiration in seconds (60-604800, default: 86400) |  ## Export Types - &#x60;url&#x60; (default): PDF is uploaded to CDN, returns JSON with URL - &#x60;binary&#x60;: Returns raw PDF bytes directly  **Credits:** 1 credit deducted per successful generation.

### Example

```ts
import {
  Configuration,
  PDFApi,
} from '@templatefox/sdk';
import type { CreatePdfOperationRequest } from '@templatefox/sdk';

async function example() {
  console.log("🚀 Testing @templatefox/sdk SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: ApiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new PDFApi(config);

  const body = {
    // CreatePdfRequest
    createPdfRequest: ...,
  } satisfies CreatePdfOperationRequest;

  try {
    const data = await api.createPdf(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **createPdfRequest** | [CreatePdfRequest](CreatePdfRequest.md) |  | |

### Return type

[**CreatePdfResponse**](CreatePdfResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`, `application/pdf`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | PDF generated successfully |  -  |
| **402** | Insufficient credits |  -  |
| **403** | Access denied - not your template |  -  |
| **404** | Template not found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

