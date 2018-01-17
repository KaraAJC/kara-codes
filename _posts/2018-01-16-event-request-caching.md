---
layout: post
title: cache it good, service worker
date:  2018-01-16
categories: til
tags: grow-with-google
permalink: /til/event-request-caching
---

Today, I'm back on my Grow With Google Scholarship course, learning about Caching.

The service worker does it's work best when it can take advantage of a cache of the requests/responses it gathers when you're online, so it can facilitate getting you the best experience possible when you're offline, or on what google says "LIE-fi".

> The Cache interface provides a storage mechanism for `Request` / `Response` object pairs that are cached, for example as part of the `ServiceWorker` life cycle.

Here are a range of methods I learned about from the Cache API, and some notes on what they're for:

```js

// Open up a local Cache
  caches.open('cache-name').then( function(cache) {
    return cache
    })

// Add a request/response pair to the cache
cache.put(request, response)

// Add a set of Req/Res pairs to the cache all at once
cache.addAll(['/things', '/stuff'])

// get out a request promise, if it exists, from the cache
cache.match(request)

// get out a request promise, if it exists, from all the caches
caches.match(request)

// Delete a cache by its name
caches.delete(cacheName)

// Retrieve the caches names
caches.keys();

```

## Resources
- MDN Docs [Cache API](https://developer.mozilla.org/en-US/docs/Web/API/Cache)
- Google Web Fundamentals [Cache and Return Reqests](https://developers.google.com/web/fundamentals/primers/service-workers/#cache_and_return_requests)
