# search-index-cookbook
### A collection of recipes and how to's on interesting use cases with [search-index](https://github.com/fergiemcdowall/search-index) (version 0.8.4)

[![Join the chat at https://gitter.im/fergiemcdowall/search-index][gitter-image]][gitter-url]
[![NPM version][npm-version-image]][npm-url]
[![NPM downloads][npm-downloads-image]][npm-url]
[![MIT License][license-image]][license-url]

Feel free to [suggest a new topic](https://github.com/eklem/search-index-cookbook/issues/new) you want explained. We've created a [simple indexer for debug purposes](https://github.com/eklem/search-index-indexer) so it's easy to test out any given JSON data set and config.

## Topics
- [Autosuggest or autocomplete - how to use the matcher](./doc/topics/autosuggest.md)
- [Create your own stopwords list, filter out the weed](./doc/topics/stopwords-filtering-away-garbage.md)
- [How to tune relevancy?](./doc/topics/field-weighting.md)
- [Index size and searching speed tradeoffs](./doc/topics/size-speed-tradeoffs.md)
- [Indexing large data sets](./doc/topics/large-datasets.md)

## Pitfalls

- [Data indexed but no search results](./doc/topics/pitfalls.md#data-indexed-but-no-search-results)

## References

- [configuration](./doc/reference/configuration.md)
- [document object](./doc/reference/document-object.md)
- [matcher](./doc/reference/matcher.md)
- [query object](./doc/reference/query-object.md)
- [search index](./doc/reference/search-index.md)
- [stopwords](./doc/reference/stopwords.md)



## TODO
Work wery much in progress. A long [list of things yet to do](https://github.com/eklem/search-index-cookbook/issues). And you're more than welcome to [suggest new recipes & topics](https://github.com/eklem/search-index-cookbook/issues/new).

[license-image]: http://img.shields.io/badge/license-MIT-blue.svg?style=flat-square
[license-url]: LICENSE

[npm-url]: https://npmjs.org/package/search-index-cookbook
[npm-version-image]: http://img.shields.io/npm/v/search-index-cookbook.svg?style=flat-square
[npm-downloads-image]: http://img.shields.io/npm/dm/search-index-cookbook.svg?style=flat-square
[gitter-url]: https://gitter.im/fergiemcdowall/search-index?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge
[gitter-image]: https://img.shields.io/badge/GITTER-join%20chat-green.svg?style=flat-square

