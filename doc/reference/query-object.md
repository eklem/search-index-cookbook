# The query object

To understand the query object, it's good to have a matching [configuration](/doc/reference/configuration.md#configuration-example) example and [document](/doc/reference/document-object.md#document-example) example

Example document object:

Matching query object

{
  "query":{
    "fieldName":[
      "queryTer "
    ]
  },
  "facets":{
    "facetOne":{
      "sort":"keyAsc"
    },
    "facetTwo":{
      "limit":10
    }
  },
  "teaser":"body",
  "maxFacetLimit":100,
  "offset":0,
  "pageSize":100
}
