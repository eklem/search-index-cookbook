# Index size and searching speed tradeoffs
`search-index` has a lot of nice features, but you should concider carefully. Especially if you are letting your users run the search engine in the browser. You don't want them to download the index forever.

Stuff that affects the index size:
- Read/write index - the possibility of re-indexing
- More than one word match in the matcher
- Fielded search
- No stopwords, few stopwords
