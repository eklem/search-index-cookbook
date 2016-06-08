# Fix 0-result queries with synonyms

Let's say you have a search solution and you do logging on your users search queries. Then it's a good idea to also log search queries that return 0 results. There are three big reasons for this:

* Your search may lack important content.
* There may be a mismatch between language used by your users and language used in your content.
* People are misspelling difficult words in their query.

For the two last issues there is a quick fix. 

## Mismatch between user language and content language
Make an array of words where the keys are the words you want to expand from, and the value is an array of alternatives. When a query contains one of the keys, the query is expanded to also contain the alternatives.

Synonyms list:
```javascript
// Synonym expansion list
[
  {
  'cab': ['taxi', 'uber']
  }
]
```

Initial query:
```javascript
[
  {
    AND: {body: ['order', cab']}
  }
]
````

Query transformed to:

```javascript
[
  {
    AND: {body: ['order', 'cab']}
  },
  {
    AND: {body: ['order', 'taxi']}
  },
  {
    AND: {body: ['order', 'uber']}
  }
]
```

## Misspelling of difficult words
Make an array of words where the key is the correct word, and the value is an array of misspelled alternatives of that word. When a query contains a word that exists as a value, you replace it with the corresponding key.

Synonyms list:
```javascript
// Misspelling contraction list
[
  {
  'vehicle': ['vehical', 'vehicule', 'vehicula', 'vechicle', 'vehiculo', 'vehicul', 'velhice', 'vehicl']
  }
]
```

Initial query:
```javascript
[
  {
    AND: {body: ['vehical', 'repair']}
  }
]
````

Query transformed to:

```javascript
[
  {
    AND: {body: ['vehicle', 'repair']}
  }
]
```
