
# TemplateListItem

Template item in list response

## Properties

Name | Type
------------ | -------------
`id` | string
`name` | string
`createdAt` | string
`updatedAt` | string

## Example

```typescript
import type { TemplateListItem } from '@templatefox/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "name": null,
  "createdAt": null,
  "updatedAt": null,
} satisfies TemplateListItem

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as TemplateListItem
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


