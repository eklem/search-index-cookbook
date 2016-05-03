# Configuration

There are some default options for `search-index`. These are set automatically, and will be used if you don't do define anything else. You can define them differently when you require the `search-index`-module.

```
  {
    deletable: true,
    fieldedSearch: true,
    indexPath: 'si',
    logLevel: 'error',
    nGramLength: [1, 2],
    stopwords: SearchIndex.getStopwords('en'),
    fieldsToStore: 'all'
  }
```

Then you can do stuff per batch, when you add stuff to the index. Anything you specify here will override anything defined in the generic options when you required the `search-index`-module. A typical use case for this is to have some general setup rules, and then you have different batches with different types of documents, and some of those batches needs a little different configuration.
```
  {
    batchName: 'my batch',
    fieldOptions: [],                                 //none
    fieldsToStore: SearchIndex.options.fieldsToStore, //inherited from initialization options
    defaultFieldOptions: defaultFieldOptions          //can be overrided per field
  }
```

And last, you have the per field options. Typically, memory and space hogging features should only be turned on per field. Filters, high nGramLengths, if the field is searchable or not, if you can have a fielded search on this field, etc.
```
{
  filter: false,
  nGramLength: SearchIndex.options.nGramLength,     //inherited from initialization options
  searchable: true,
  weight: 1,
  fieldedSearch: SearchIndex.options.fieldedSearch  //inherited from initialization options
}
```

## Configuration example
!! More to come. Should match query object example and document object example

```
  [
    {'Document example ...'}
  ]

```
```
  [
    {'Config example ...'}
  ]

```


# Document object

A document or item object always consist of at least two fields. An `id`-field and then at least one field for content. If you don't specify an id, `search-index` will create one.

## Document example
This example is to better help you understand the connection between [configuration](#configuration-example), the content / document / item going into the index, and the [query object](#query-object), getting the stuff out again.

... more to come ...


# Matcher
Most search engines has a matcher and a searcher. While the searcher is trying to find documents, the matcher tries to find words or terms. [`search-index` uses the matcher](https://github.com/fergiemcdowall/search-index/blob/master/doc/autosuggest.md#autosuggest-and-matching) to find words/terms that starts with what the user is typing and that is present in the documents. It sorts these terms with most used first.


# Query object

To understand the query object, it's good to have a matching [configuration](configuration.md#configuration-example) example and [document](document-object.md#document-example) example.

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
  "categories":{
    "field": "categoryName",
    "sort":"keyAsc",
    "limit":10
  },
  "teaser":"body",
  "offset":0,
  "pageSize":100
}
```


# search index

`search-index` is a search index that consists of two parts.

## Document index
One contains the documents or items, divided into fields. It has at least two fields, an `id`-field and at a minimum, a `content`-field. These are the ones you have available to show as search results. The searcher is used to search within these documents.

## Term index
The other is more like the index in the back of any book. It a list of words/terms that are present within the document corpus, or at least the ones that bears any meaning. These words/terms have references to the documents where they are present.

## The words bearing no meaning
For `search-index`, it's the [stopwords](stopwords) list that decides which word does not bear any meaning. It's used to weed out words you don't want to have in the Term index.


# Stopwords

Stopwords is a list that contains a lot of small words bearing little or no meaning, and thus doesn't help in distinguishing documents from each other. These words are therefore stripped from away from the [word / term index](#term-index) that the matcher uses, but not from the actual documents.

## Default stopword list configuration
```javascript
  {
    stopwords: SearchIndex.getStopwords('en'),
  }
```

## Stopwords for the English language
```javascript
[
  'about', 'after', 'all', 'also', 'am', 'an', 'and', 'another', 'any', 'are', 'as', 'at', 'be',
  'because', 'been', 'before', 'being', 'between', 'both', 'but', 'by', 'came', 'can',
  'come', 'could', 'did', 'do', 'each', 'for', 'from', 'get', 'got', 'has', 'had',
  'he', 'have', 'her', 'here', 'him', 'himself', 'his', 'how', 'if', 'in', 'into',
  'is', 'it', 'like', 'make', 'many', 'me', 'might', 'more', 'most', 'much', 'must',
  'my', 'never', 'now', 'of', 'on', 'only', 'or', 'other', 'our', 'out', 'over',
  'said', 'same', 'see', 'should', 'since', 'some', 'still', 'such', 'take', 'than',
  'that', 'the', 'their', 'them', 'then', 'there', 'these', 'they', 'this', 'those',
  'through', 'to', 'too', 'under', 'up', 'very', 'was', 'way', 'we', 'well', 'were',
  'what', 'where', 'which', 'while', 'who', 'with', 'would', 'you', 'your',
  'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n',
  'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z', '$', '1',
  '2', '3', '4', '5', '6', '7', '8', '9', '0', '_']
```

## Available languages for stopword lists
[Supported languages](https://github.com/fergiemcdowall/stopword/tree/master/lib): en, es, fa, fr, it, ja, nl, no, pl, pt, ru, zh.

