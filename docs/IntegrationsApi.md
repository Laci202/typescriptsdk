# IntegrationsApi

All URIs are relative to *https://api.pdftemplateapi.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**deleteS3Config**](IntegrationsApi.md#deletes3config) | **DELETE** /v1/integrations/s3 | Delete S3 configuration |
| [**getS3Config**](IntegrationsApi.md#gets3config) | **GET** /v1/integrations/s3 | Get S3 configuration |
| [**saveS3Config**](IntegrationsApi.md#saves3config) | **POST** /v1/integrations/s3 | Save S3 configuration |
| [**testS3Connection**](IntegrationsApi.md#tests3connection) | **POST** /v1/integrations/s3/test | Test S3 connection |



## deleteS3Config

> S3SuccessResponse deleteS3Config()

Delete S3 configuration

Delete S3 storage configuration.  **Authentication:** API Key required (&#x60;x-api-key&#x60; header) with admin privileges  **Usage:** Remove your S3 integration. Generated PDFs will use the default CDN storage after deletion.  **Warning:** This action is irreversible. You\&#39;ll need to reconfigure S3 to use it again.  **No credits consumed:** This is a configuration endpoint.

### Example

```ts
import {
  Configuration,
  IntegrationsApi,
} from '@templatefox/sdk';
import type { DeleteS3ConfigRequest } from '@templatefox/sdk';

async function example() {
  console.log("🚀 Testing @templatefox/sdk SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: ApiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new IntegrationsApi(config);

  try {
    const data = await api.deleteS3Config();
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

[**S3SuccessResponse**](S3SuccessResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Configuration deleted successfully |  -  |
| **403** | Admin privileges required |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getS3Config

> S3ConfigResponse getS3Config()

Get S3 configuration

Get current S3 storage configuration.  **Authentication:** API Key required (&#x60;x-api-key&#x60; header) with admin privileges  **Usage:** Retrieve your S3 integration settings. Secret access key is masked for security.  **Returns 404** if S3 is not configured.  **No credits consumed:** This is a read-only endpoint.

### Example

```ts
import {
  Configuration,
  IntegrationsApi,
} from '@templatefox/sdk';
import type { GetS3ConfigRequest } from '@templatefox/sdk';

async function example() {
  console.log("🚀 Testing @templatefox/sdk SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: ApiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new IntegrationsApi(config);

  try {
    const data = await api.getS3Config();
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

[**S3ConfigResponse**](S3ConfigResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | S3 configuration retrieved successfully |  -  |
| **403** | Admin privileges required |  -  |
| **404** | S3 is not configured |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## saveS3Config

> S3SuccessResponse saveS3Config(s3ConfigRequest)

Save S3 configuration

Save or update S3-compatible storage configuration.  **Authentication:** API Key required (&#x60;x-api-key&#x60; header) with admin privileges  **Usage:** Configure your S3-compatible storage to receive generated PDFs directly in your own bucket instead of the default CDN.  **Supported providers:** - Amazon S3 - DigitalOcean Spaces - Cloudflare R2 - MinIO - Any S3-compatible storage  **Secret key behavior:** - For new configuration: &#x60;secret_access_key&#x60; is required - For updates: Omit &#x60;secret_access_key&#x60; to keep existing value  **No credits consumed:** This is a configuration endpoint.

### Example

```ts
import {
  Configuration,
  IntegrationsApi,
} from '@templatefox/sdk';
import type { SaveS3ConfigRequest } from '@templatefox/sdk';

async function example() {
  console.log("🚀 Testing @templatefox/sdk SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: ApiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new IntegrationsApi(config);

  const body = {
    // S3ConfigRequest
    s3ConfigRequest: ...,
  } satisfies SaveS3ConfigRequest;

  try {
    const data = await api.saveS3Config(body);
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
| **s3ConfigRequest** | [S3ConfigRequest](S3ConfigRequest.md) |  | |

### Return type

[**S3SuccessResponse**](S3SuccessResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Configuration saved successfully |  -  |
| **400** | Invalid configuration (e.g., missing secret key for new config) |  -  |
| **403** | Admin privileges required |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## testS3Connection

> S3TestResponse testS3Connection()

Test S3 connection

Test S3 connection with stored credentials.  **Authentication:** API Key required (&#x60;x-api-key&#x60; header) with admin privileges  **Usage:** Verify your S3 configuration is working correctly. The test will: 1. Connect to the endpoint 2. Verify bucket access 3. Check write permissions by uploading a small test file  **Prerequisite:** S3 must be configured first using &#x60;POST /v1/integrations/s3&#x60;  **No credits consumed:** This is a diagnostic endpoint.

### Example

```ts
import {
  Configuration,
  IntegrationsApi,
} from '@templatefox/sdk';
import type { TestS3ConnectionRequest } from '@templatefox/sdk';

async function example() {
  console.log("🚀 Testing @templatefox/sdk SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: ApiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new IntegrationsApi(config);

  try {
    const data = await api.testS3Connection();
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

[**S3TestResponse**](S3TestResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Connection test successful |  -  |
| **400** | Connection test failed |  -  |
| **403** | Admin privileges required |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

