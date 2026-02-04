
# Transaction

Transaction record

## Properties

Name | Type
------------ | -------------
`transactionRef` | string
`transactionType` | string
`templateId` | string
`execTm` | number
`credits` | number
`createdAt` | string

## Example

```typescript
import type { Transaction } from '@templatefox/sdk'

// TODO: Update the object below with actual values
const example = {
  "transactionRef": null,
  "transactionType": null,
  "templateId": null,
  "execTm": null,
  "credits": null,
  "createdAt": null,
} satisfies Transaction

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as Transaction
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


