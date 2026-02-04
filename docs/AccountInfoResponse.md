
# AccountInfoResponse

Response for account info endpoint

## Properties

Name | Type
------------ | -------------
`credits` | number
`email` | string

## Example

```typescript
import type { AccountInfoResponse } from '@templatefox/sdk'

// TODO: Update the object below with actual values
const example = {
  "credits": null,
  "email": null,
} satisfies AccountInfoResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AccountInfoResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


