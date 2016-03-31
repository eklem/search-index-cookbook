# Pitfalls when developing with search-index

## Data indexed, but no search results
An error that is easy to do when you have indexed some content, and want to check if the content actually was indexed right, is to search with a word that exists in the list of stopwords. This, and the fact that search-index only does AND-searches, makes a query containing any stopword return 0 results.



## Facets / filters not working
This is easy to do wrong when you have a facet with only one filter per document. For a facet `tags`, the filter should still be an array, even if only an array of one.

Example:
```javascript
[
    {
        "date": 1415780040000,
        "title": "My title",
        "text": "Some text that fits the title",
        "tags": [
            "json"
        ],
        "id": "3UqUi1"
    }
]
```
