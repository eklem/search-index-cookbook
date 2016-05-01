# Pitfalls when developing with search-index

## Data indexed, but no search results
An error that is easy to do when you have indexed some content, and want to check if the content actually was indexed right, is to search with a word that exists in the list of stopwords. If using an AND-query and the query contains one or more stopwords, `search-index` will return 0 results.
