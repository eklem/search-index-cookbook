# search-index-cookbook
A collection of recipes and how to's on interesting use cases with [search-index](https://github.com/fergiemcdowall/search-index)
Feel free to [suggest a new topic](https://github.com/eklem/search-index-cookbook/issues/new) you want explained. We've created a [simple indexer for debug purposes](/eklem/search-index-indexer) so it's easy to test out any given JSON data set and config.

## Topics

- [Autosuggest: How to use the matcher](doc/topics/autosuggest.md)
- [Create your own stopwords list, filter out the weed](doc/topics/stopwords-filtering-away-garbage.md)
- [How to tune relevancy?](doc/topics/field-weighting.md)
- [Index size and searching speed tradeoffs](doc/topics/size-speed-tradeoffs.md)

## Pitfalls

- [Data indexed but no search results](doc/topics/pitfalls.md#data-indexed-but-no-search-results)
- [Facets / filters not working](doc/topics/pitfalls.md#facets--filters-not-working)

## References

- [search index](doc/reference/search-index.md)
- [stopwords](doc/reference/stopwords.md)



## TODO
### Recipes / topics:
- [ ] Autosuggest / autocomplete (matcher) (with more than one word)
- [ ] Enabling search from the browser search box
- [ ] Indexing only for an autocomplete function
- [ ] "Phrase search"
- [ ] Faceted/filtered search
- [ ] Price & geographical filtering with filter ranges
- [ ] Hit highlighting
- [x] Stopwords
- [x] Weighting fields: Strategies for weighting fields indexing and query side
- [ ] Fielded search
- [ ] Running in the browser
- [ ] Offline searching
- [ ] Features vs. index file size
- [ ] Percolator, or how to set up query subscription 

### Reference
- [x] The index - How does it work
- [ ] The index - matcher
- [x] Pitfalls when developing with search-index
- [ ] The indexing config object
- [ ] The query object
- [x] Stopwords


### Cookbook will contain three parts:
- Recipes documentation
- Example code (interactive indexers, matchers, searchers) running in the browser. Or example code working with search-index-indexer.
- References chapter

