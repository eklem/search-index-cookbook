# Pitfalls when developing with search-index

## Data indexed, but no search results
An error that is easy to do when you have indexed some content, and want to check if the content actually was indexed right, is to search with a word that exists in the list of stopwords. This, and the fact that search-index only does AND-searches, makes a query containing any stopword return 0 results.
