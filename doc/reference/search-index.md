# The search index and how it works

`search-index` is a search index that consists of two parts.

## Document index
One contains the documents or items, divided into fields. It has at least two fields, an `id`-field and at a minimum, a `content`-field. These are the ones you have available to show as search results. The searcher is used to search within these documents.

## Term index
The other is more like the index in the back of any book. It a list of words/terms that are present within the document corpus, or at least the ones that bears any meaning. These words/terms have references to the documents where they are present.

## The words bearing no meaning
For `search-index`, it's the [stopwords](stopwords.md) list that decides which word does not bear any meaning. It's used to weed out words you don't want to have in the Term index.
