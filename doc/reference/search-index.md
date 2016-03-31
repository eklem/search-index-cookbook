# The search index and how it works

`search-index` is a search index that consists of two parts. 

## Document index
One contains the documents or items, divided into fields. It has at least two fields, an `id`-field and at a minimum, a `content`-field. This is what you have available to show as search results.

## Word index
The other is more like the index in the back of any book. It consists of almost all the words in the book, or at least the ones that bears any meaning. These words have references to the documents they are in.

## The words bearing no meaning
For `search-index`, it's the [stopwords](stopwords.md) list that decides which word does not bear any meaning.