# How to index really large datasets

`search-index` was initially built for small data, but there's proof of 1.3 million documents indexed so far, and it seems it will be possible to go a lot furter. But to get these datasets in, you have to do at least two things.

## Batch size
There's a lot of relevance calculation per batch of document you index, so it's faster to have big batches. For a batch, every key that will go into the index is held in memory. So the downside with big batches are increased memory use. The example with 1.3 million documents was solved by splitting it into batches of 10.000 documents.

## Setting memory available
Node can also run out of memory. This means you have to increase the memory `node` has available to ensure the process doesn't run out of memory. Easily done by:

```
$ node --max-old-space-size=8192 [your indexing script]
```

## Further optimization

[to come]
