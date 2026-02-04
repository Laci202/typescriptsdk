
# CreatePdfRequest

Request model for PDF generation

## Properties

Name | Type
------------ | -------------
`templateId` | string
`data` | { [key: string]: any; }
`exportType` | [ExportType](ExportType.md)
`expiration` | number
`filename` | string
`storeS3` | boolean
`s3Filepath` | string
`s3Bucket` | string

## Example

```typescript
import type { CreatePdfRequest } from '@templatefox/sdk'

// TODO: Update the object below with actual values
const example = {
  "templateId": null,
  "data": null,
  "exportType": null,
  "expiration": null,
  "filename": null,
  "storeS3": null,
  "s3Filepath": null,
  "s3Bucket": null,
} satisfies CreatePdfRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreatePdfRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


