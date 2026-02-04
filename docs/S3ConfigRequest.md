
# S3ConfigRequest

Request model for S3 configuration

## Properties

Name | Type
------------ | -------------
`endpointUrl` | string
`accessKeyId` | string
`secretAccessKey` | string
`bucketName` | string
`defaultPrefix` | string

## Example

```typescript
import type { S3ConfigRequest } from '@templatefox/sdk'

// TODO: Update the object below with actual values
const example = {
  "endpointUrl": null,
  "accessKeyId": null,
  "secretAccessKey": null,
  "bucketName": null,
  "defaultPrefix": null,
} satisfies S3ConfigRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as S3ConfigRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


