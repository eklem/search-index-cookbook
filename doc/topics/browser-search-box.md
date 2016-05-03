# Browser search with autosuggest


## What you need
- A search index
- norch (with search-index) installed, pointing to your search index
- A frontend, i.e norch-angular-app or your frontend

## Duplicate the norch matcher
You don't have to duplicate it, but okay to not ruin your search solution's autosuggest, if you have one.

Call it opensearchsuggest. It will be the endpoint that the opensearch.xml reference to, and that the browser searchbox talks to.

### What the matcher returns out of the box:
For "que" as the query:

```json
["query",
 "query suggestion",
 "query completion"
]
```

### What you want it to return:
For "que" as the query:

```json
["que",
  ["query",
   "query suggestion",
   "query completion"
  ]
]
```
So you want it to return the actuall query as well.


## opensearch.xml
On your webserver / webapp root, create the file opensearch.xml. Change the `[URL]` to your URL:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<OpenSearchDescription xmlns="http://a9.com/-/spec/opensearch/1.1/">
    <ShortName>Life Index</ShortName>
    <Description>Your digital life searchable</Description>
    <Tags>search</Tags>
    <Contact>[your.email@address.com]</Contact>
    <Image height="16" width="16" type="image/x-icon">http://[URL]:3030/images/favicon.ico</Image>
    <Image height="64" width="64" type="image/png">http://[URL]:3030/images/favicon.png</Image>
    <Url type="application/x-suggestions+json"
        rel="suggestions" method="GET"
        template="http://[URL]:3030/opensearchsuggests?beginsWith={searchTerms}" />
    <Url type="text/html" method="GET"
        template="http://[URL]:3030/#/search?q={searchTerms}&amp;facets=user,type,tags"/>
</OpenSearchDescription>
```

## Reference from index.html

```html
<html>
    <head profile="http://a9.com/-/spec/opensearch/1.1/">
    <!--- ... --->
        <link rel="search"
            type="application/opensearchdescription+xml"
            href="http://[URL]/opensearch.xml"
            title="[Site] Search" />
        </head>
   <body>
    ...
   </body>
</html>

```

