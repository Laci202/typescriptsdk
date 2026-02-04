
# S3SuccessResponse

Generic success response for S3 operations

## Properties

Name | Type
------------ | -------------
`success` | boolean

## Example

```typescript
import type { S3SuccessResponse } from '@templatefox/sdk'

// TODO: Update the object below with actual values
const example = {
  "success": null,
} satisfies S3SuccessResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as S3SuccessResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


