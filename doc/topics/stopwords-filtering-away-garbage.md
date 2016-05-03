# Create your own stopwords list, filter out the weed
A list of stopwords is not very long, and creating one yourself is quite easy. This could have some nice advantages.

## Multiple language document corpus
If your document corpus consists of several languages, just compile your own [stopwords](../reference/references.md#stopwords) list. Mostly, the languages doesn't interfeer with each other. A

## Smaller index, bearing more meaning
The stopwords lists are really small, and if you look through your documents, they will still contain a lot of not so meaningfull words. Add more words to your list, and get a smaller, faster and more meaningfull index. There are two downsides. If your users use a lot of small words / natural language when they search, [they will get 0 results back](pitfalls.md#data-indexed-but-no-search-results). And you get a higher CPU usage during indexing / longer indexing time.
