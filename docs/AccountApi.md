# AccountApi

All URIs are relative to *https://api.pdftemplateapi.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getAccount**](AccountApi.md#getaccount) | **GET** /v1/account | Get account info |
| [**listTransactions**](AccountApi.md#listtransactions) | **GET** /v1/account/transactions | List transactions |



## getAccount

> AccountInfoResponse getAccount()

Get account info

Get account information including remaining credits.  **Authentication:** API Key required (&#x60;x-api-key&#x60; header) or JWT token  **Usage:** Check credit balance before performing operations.  **No credits consumed:** This is a read-only endpoint.

### Example

```ts
import {
  Configuration,
  AccountApi,
} from '@templatefox/sdk';
import type { GetAccountRequest } from '@templatefox/sdk';

async function example() {
  console.log("🚀 Testing @templatefox/sdk SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: ApiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new AccountApi(config);

  try {
    const data = await api.getAccount();
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

[**AccountInfoResponse**](AccountInfoResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Account information |  -  |
| **403** | Invalid or missing API key |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listTransactions

> TransactionsResponse listTransactions(limit, offset)

List transactions

List transaction history for the authenticated user.  **Authentication:** API Key required (&#x60;x-api-key&#x60; header) or JWT token  **Pagination:** Use &#x60;limit&#x60; and &#x60;offset&#x60; query parameters.  **Transaction types:** - &#x60;PDFGEN&#x60;: PDF generation (consumes credits) - &#x60;REFUND&#x60;: Credit refund (on failed generation) - &#x60;PURCHASE&#x60;: Credit purchase - &#x60;BONUS&#x60;: Bonus credits  **Credits field:** - Positive value &#x3D; credits consumed - Negative value &#x3D; credits added  **No credits consumed:** This is a read-only endpoint.

### Example

```ts
import {
  Configuration,
  AccountApi,
} from '@templatefox/sdk';
import type { ListTransactionsRequest } from '@templatefox/sdk';

async function example() {
  console.log("🚀 Testing @templatefox/sdk SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: ApiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new AccountApi(config);

  const body = {
    // number | Number of records to return (optional)
    limit: 56,
    // number | Number of records to skip (optional)
    offset: 56,
  } satisfies ListTransactionsRequest;

  try {
    const data = await api.listTransactions(body);
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
| **limit** | `number` | Number of records to return | [Optional] [Defaults to `300`] |
| **offset** | `number` | Number of records to skip | [Optional] [Defaults to `0`] |

### Return type

[**TransactionsResponse**](TransactionsResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Transaction history |  -  |
| **403** | Invalid or missing API key |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

