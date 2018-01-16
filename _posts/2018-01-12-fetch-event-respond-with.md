---
layout: post
title: respondWith and Fetch Events
date:  Fri Jan 12 16:04:15 CST 2018
categories: til
tags: service-worker fetch-api web grow-with-google
permalink: /til/fetch-events
---

Today, in the continuation of my Grow With Google Udacity Scholarship, I learned about the Service Worker life cycle, and how to set up the service worker to HIJACK the requests!

in particular, I learned about the `respondWith` method, which in its basic form looks like this:

```js

self.addEventListener('fetch', function(event) {

    event.respondWith(
      new Response("I'm the body", {
        status: 200,
        headers: {
          'Content-Type': 'Text/Html'
        }
      })
    );

});
```

this function takes a promise that resolves to a Response object, with a body blob and optionally an object filled with further config info for the response, like headers etc.

more complex uses of this method will involve `fetch`, more promise configs like `async/await`, or `catch` and some conditionals. I'm off to learn those now!

## Resources

- MDN Docs: [Response Object](https://developer.mozilla.org/en-US/docs/Web/API/Response/Response)
- MDN Docs: [FetchEvent.respondWith()](https://developer.mozilla.org/en-US/docs/Web/API/Fetchevent/respondWith)