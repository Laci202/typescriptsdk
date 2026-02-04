
# TemplatesListResponse

Response for template list endpoint

## Properties

Name | Type
------------ | -------------
`templates` | [Array&lt;TemplateListItem&gt;](TemplateListItem.md)

## Example

```typescript
import type { TemplatesListResponse } from '@templatefox/sdk'

// TODO: Update the object below with actual values
const example = {
  "templates": null,
} satisfies TemplatesListResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as TemplatesListResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


