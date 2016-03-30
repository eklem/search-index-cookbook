# Strategies for getting the best documents on top for any given query term

## The relevancy model in search-index: tf-idf

Most search engines have a relevancy model based on `tf-idf` or something similar. It's short for `term frequency - inverse document frequency`. `term-frequency` means that a document with the highest frequency of the words from your query term, is the most important. `inverse document frequency` means that the words in your query term that is less used within all of your documents, the document corpus, is the most imortant words. These seldom used words better distinguish a document from other documents, and give them a higher uniqueness.

## How to tune relevancy: field weighting

The default field weight in `search-index` is 1, and this can be set independently per field. In the example below, the field `tags` is set more important than the field `title`, which is again set more important than the field `body`. So a word from your query term found in the `tags`-field gives that document a higher score, than if the word was found the same amount of time in the `title`- or `body`-field.

Example:
```json
fieldOptions: [
  {fieldName: 'title',  weight: 2},
  {fieldName: 'tags',  weight: 3},
  {fieldName: 'body', weight: 1}
  ]
```

### Some documents better than others?

Good knowledge of who your users are, and what your document corpus contains is alfa and omega for creating good search relevancy. Are there some type of documents that are more important for your users, than others? `search-index` can only set field weight on a batch level, but you decide how many, and which documents each batch consists of. If you have a type of documents that are percieved as having a better quality among your users, you could weight the fields for these documents higher, by indexing them in a separate batch, with a separate `fieldOptions` config.

### How to be smart about your relevancy tuning

It's easy to "fix one, break one" when tuning relevancy for a search engine. Often you figure out that some document is not found high enough in your search result for a give query term. You fix it, but at the same time, you could ruin one or more search terms you weren't tuning for. The teqnique to solve this is to create a benchmark of queries. Probably you have a most used query terms list, or you could aggregate this from a query log. From this list you create in example a to 10 or top 100 most important queries list. For each of these queries, you define one or more search results that should each be within top [n] search results.

So, when you find a document that shuld have come higher up in your search result for a query, you test-tune for that, and see if you manage to get it higher, without breaking the existing benchmark rules.

### Garbage in, garbage out

Very often, the quality of the document corpus is not good enough. You tweak and tune, but it is impossible to improve for some type of queries without ruining it for others. If you, or your organisation, owns the documents, maybe it's time to update them.

## Field weighting, query side

!!! To come [when the query side field weighting is better documented](https://github.com/fergiemcdowall/search-index/issues/247)
- freshness
- seasonal changes
- no re-indexing (this is a poor reason, but valid every now and then)
