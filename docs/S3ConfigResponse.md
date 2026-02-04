
# S3ConfigResponse

Response for S3 configuration (with masked secret)

## Properties

Name | Type
------------ | -------------
`configured` | boolean
`endpointUrl` | string
`accessKeyId` | string
`secretAccessKeyMasked` | string
`bucketName` | string
`defaultPrefix` | string

## Example

```typescript
import type { S3ConfigResponse } from '@templatefox/sdk'

// TODO: Update the object below with actual values
const example = {
  "configured": null,
  "endpointUrl": null,
  "accessKeyId": null,
  "secretAccessKeyMasked": null,
  "bucketName": null,
  "defaultPrefix": null,
} satisfies S3ConfigResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as S3ConfigResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


