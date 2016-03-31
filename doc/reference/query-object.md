# The query object

To understand the query object, it's good to have a matching [configuration](/doc/reference/configuration.md#configuration-example) example and [document](/doc/reference/document-object.md#document-example) example.

A nice thing about the query object is that is's JSON. That has some benefits:

- It easy to describe your query precicely
- Linking to a search result
- Creating links that utilise hidden features

## Query object example

```json
{
  "query":{
    "fieldName":[
      "query"
    ]
  },
  "facets":{
    "facetName":{
      "sort":"keyAsc",
      "limit":10
    }
  },
  "teaser":"body",
  "maxFacetLimit":100,
  "offset":0,
  "pageSize":100
}
```