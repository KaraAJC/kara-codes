---
layout: post
title: service workers
date:  2018-01-10
categories: til
tags: offline-first PWA Web-APIs GrowWithGoogle Mobile-Web-Specialist Udacity
permalink: /til/service-workers-intro
---

Today I was informed of my acceptance into the Grow With Google Scholarship in the Mobile Web Specialist track!🎉
![Udacity Scholarship Badge](https://s3-us-west-2.amazonaws.com/udacity-email/Scholarships/GrowWithGoogleDeveloperChallengeScholarship.png?utm_medium=email&utm_campaign=sch_600_auto_ndxxx_accepted-gwg&utm_source=blueshift&utm_content=sch_600_auto_ndxxx_accepted-gwg&bsft_eid=0278905a-c28b-4a40-852e-38bdcbd095b7&bsft_clkid=e786d1c4-a79e-409d-a528-903cd2736f40&bsft_uid=04bccbf8-86ac-40af-ac38-755d2002eebd&bsft_mid=c618d3cd-9d86-4ccd-9959-ec0953394de6&bsft_txnid=cce569b8-09b2-4c78-9ea3-5a8a625bfa46)

I've got 3 months to hone my skills on new web development technologies, and the first few lessons are focused on **Offline First** Development.

I'd heard of the term in the past year, as Google did a PWA Tour, and I got to go to the Chicago event, but I'm happy to jump back into the concept of how the Service Worker API will help us get to an offline-first environment on the web.

So two terms I've mentioned: `offline-first` and `service worker`.

**Offline-First** is a way to consider what the web should do when there's little, or no connectivity, that doesnt leave us with blank pages. There's lots of data our devices hold onto when we interact with sites, why not make it so we're taking advantage of that data in an offline environment? This is what offline-first guides us towards. Consider what the user should be able to do in little to no connectivity _first_.

**Service Workers** are how we get to do that. Because there are a few decisions that need to be made depending on what's being requested and whether there's something existing in cache or whether it can be fetched, a Service Worker is registered on the browser to facilitate that, so in the case that there is little/no connectivity, things can be pulled from cache, and the service worker can keep an eye on connectivity to fetch and sync new data as things come back online.

You can access the Service Worker API through the Navigator object, which is basically the User Agent you're interfacing with.

On page load, you call the Navigator to register the service worker, and from there, the Service Worker listens to events, and dispatches actions depending on what you've asked it to do in any given network scenario.

```js

  // Code from Mozilla's web docs: 
  // https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer/register

// in your main.js
    if ('serviceWorker' in navigator) {
    // Register a service worker hosted at the root of the
    // site using the default scope.
    navigator.serviceWorker.register('/sw.js').then(function(registration) {
      console.log('Service worker registration succeeded:', registration);
    }).catch(function(error) {
      console.log('Service worker registration failed:', error);
    });
    } else {
      console.log('Service workers are not supported.');
    }

// in your sw.js
  self.addEventListener('fetch', function(event) {
      // magic goes here
  });
```

## Resources
I'm a visual learner, so I've appreciated the Udacity lessons so far, and I've enjoyed diving in a bit more into the following sites:
- Mozilla Web Docs: [Using Service Workers tutorial](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API/Using_Service_Workers)
- Medium Article [Offline First: The decentralized web and peer-to-peer technologies](https://medium.com/offline-camp/offline-first-the-decentralized-web-and-peer-to-peer-technologies-b05b7fb3bcdd) (it's a bit old, but fascinating! also there's an OFFLINE CAMP?!)
- a list of offline-first, Progressive Web Apps [PWA.Rocks!](https://pwa.rocks/ ) (My FAVE is paper planes!)
- Google Developers Web Fundamentals: [Intro to service workers](https://developers.google.com/web/fundamentals/primers/service-workers/)
