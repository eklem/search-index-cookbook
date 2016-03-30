#Pitfalls when developing with search-index

##Data indexed, but no search results
An error that is easy to do when you have indexed some content, and want to check if the content actually was indexed right, is to search with a word that exists in the list of stopwords. This, and the fact that search-index only does AND-searches, makes a query containing any stopword return 0 results.

A list of stopwords is a list that contains a lot of small words bearing little or no meaning, and thus doesn't help in distinguishing documents from each other. These words are therefore stripped from away from the word index.

###Default stopword list configuration 
```json
  {
    stopwords: SearchIndex.getStopwords('en'),
  }
```

###Stopwords for the English language
```javascript
[
  'about', 'after', 'all', 'also', 'am', 'an', 'and', 'another', 'any', 'are', 'as', 'at', 'be',
  'because', 'been', 'before', 'being', 'between', 'both', 'but', 'by', 'came', 'can',
  'come', 'could', 'did', 'do', 'each', 'for', 'from', 'get', 'got', 'has', 'had',
  'he', 'have', 'her', 'here', 'him', 'himself', 'his', 'how', 'if', 'in', 'into',
  'is', 'it', 'like', 'make', 'many', 'me', 'might', 'more', 'most', 'much', 'must',
  'my', 'never', 'now', 'of', 'on', 'only', 'or', 'other', 'our', 'out', 'over',
  'said', 'same', 'see', 'should', 'since', 'some', 'still', 'such', 'take', 'than',
  'that', 'the', 'their', 'them', 'then', 'there', 'these', 'they', 'this', 'those',
  'through', 'to', 'too', 'under', 'up', 'very', 'was', 'way', 'we', 'well', 'were',
  'what', 'where', 'which', 'while', 'who', 'with', 'would', 'you', 'your',
  'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n',
  'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z', '$', '1',
  '2', '3', '4', '5', '6', '7', '8', '9', '0', '_']
```


###Available languages for stopword lists
[Supported languages](https://github.com/fergiemcdowall/stopword/tree/master/lib): en, es, fa, fr, it, ja, nl, no, pl, pt, ru, zh. The lists are not very long, and creating one yourself is quite easy.
