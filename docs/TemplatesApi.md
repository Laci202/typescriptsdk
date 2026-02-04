# TemplatesApi

All URIs are relative to *https://api.pdftemplateapi.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getTemplateFields**](TemplatesApi.md#gettemplatefields) | **GET** /v1/templates/{template_id}/fields | Get template fields |
| [**listTemplates**](TemplatesApi.md#listtemplates) | **GET** /v1/templates | List templates |



## getTemplateFields

> Array&lt;TemplateField&gt; getTemplateFields(templateId)

Get template fields

Get the dynamic fields for a template.  **Authentication:** API Key required (&#x60;x-api-key&#x60; header) or JWT token  **Usage:** This endpoint is designed for Zapier Dynamic Fields integration. It returns an array of field definitions that Zapier uses to dynamically generate input forms.  **Response format:** Array of objects compatible with Zapier InputFieldsSchema. Each field has: &#x60;key&#x60;, &#x60;label&#x60;, &#x60;type&#x60;, &#x60;required&#x60;, and optional &#x60;helpText&#x60;.  **Field types:** - &#x60;string&#x60;: Text input (also used for JSON arrays/objects) - &#x60;integer&#x60;: Integer number - &#x60;number&#x60;: Decimal number - &#x60;boolean&#x60;: True/False checkbox  **Arrays and objects:** Complex types are returned as &#x60;string&#x60; type with a &#x60;helpText&#x60; showing the expected JSON format.  **No credits consumed:** This is a read-only endpoint.

### Example

```ts
import {
  Configuration,
  TemplatesApi,
} from '@templatefox/sdk';
import type { GetTemplateFieldsRequest } from '@templatefox/sdk';

async function example() {
  console.log("🚀 Testing @templatefox/sdk SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: ApiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new TemplatesApi(config);

  const body = {
    // string
    templateId: templateId_example,
  } satisfies GetTemplateFieldsRequest;

  try {
    const data = await api.getTemplateFields(body);
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
| **templateId** | `string` |  | [Defaults to `undefined`] |

### Return type

[**Array&lt;TemplateField&gt;**](TemplateField.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of template fields |  -  |
| **403** | Invalid or missing API key |  -  |
| **404** | Template not found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listTemplates

> TemplatesListResponse listTemplates()

List templates

List all templates for the authenticated user.  **Authentication:** API Key required (&#x60;x-api-key&#x60; header) or JWT token  **Usage:** This endpoint is designed for no-code tools (Zapier, Make, n8n) to populate template selection dropdowns.  **No credits consumed:** This is a read-only endpoint.

### Example

```ts
import {
  Configuration,
  TemplatesApi,
} from '@templatefox/sdk';
import type { ListTemplatesRequest } from '@templatefox/sdk';

async function example() {
  console.log("🚀 Testing @templatefox/sdk SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: ApiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new TemplatesApi(config);

  try {
    const data = await api.listTemplates();
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**TemplatesListResponse**](TemplatesListResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of templates |  -  |
| **403** | Invalid or missing API key |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

