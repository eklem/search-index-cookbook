# Autosuggest or autocomplete - how to use the matcher

Most search engines has a [matcher](../reference/references.md#matcher) and a searcher. The matcher picks words or terms that starts with what the user is typing. The matched term can then be used as a query for the searcher. The searcher searches within the documents.

The term index is a reverse index / inverted index. How many letter to type before the matcher tries to match is a configuration value.

## nGramLength
How long the terms can be is defined by the [nGramLength option](../reference/references.md#configuration.) when adding documents to the search engine.

## Stopwords
If you have defined a [stopwords](../reference/references.md#stopwords) list, these wil not be available for the matcher.
