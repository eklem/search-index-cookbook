# Configuration

There are some default options for `search-index`. These are set automatically, and will be used if you don't do define anything else. You can define them differently when you require the `search-index`-module.

```json
  {
    deletable: true,
    fieldedSearch: true,
    indexPath: 'si',
    logLevel: 'error',
    nGramLength: 1,
    stopwords: SearchIndex.getStopwords('en'),
    fieldsToStore: 'all'
  }
```

Then you can do stuff per batch, when you add stuff to the index. Anything you specify here will override anything defined in the generic options when you required the `search-index`-module. A typical use case for this is to have some general setup rules, and then you have different batches with different types of documents, and some of those batches needs a little different configuration.
```json
  {
    batchName: 'my batch',
    fieldOptions: [],                                 //none
    fieldsToStore: SearchIndex.options.fieldsToStore, //inherited from initialization options
    defaultFieldOptions: defaultFieldOptions          //can be overrided per field  
  }
```

And last, you have the per field options. Typically, memory and space hogging features should only be turned on per field. Filters, high nGramLengths, if the field is searchable or not, if you can have a fielded search on this field, etc.
```json
{
  filter: false,
  nGramLength: SearchIndex.options.nGramLength,     //inherited from initialization options
  searchable: true,
  weight: 1,
  fieldedSearch: SearchIndex.options.fieldedSearch  //inherited from initialization options
}
```

## A full batch and field configuration example
!! More to come

```json
  [
    {'Document example ...'}
  ]

```
```json
  [
    {'Config example ...'}
  ]

```