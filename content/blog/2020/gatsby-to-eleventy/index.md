---
title: Delete Service Workers to Leave Gatsby
date:  '20201102'
layout: post
tags: [javascript, gatsby, eleventy, service-workers]
---

I've switched away from Gatsby to Eleventy. One thing my Gatsby site had done (some of the "magic") was generate and register a Service Worker for offline/caching reasons.

When I switched to Eleventy, browsers did not automatically show the new site unless I held shift while clicking refresh.

The hot tip here is to destroy the service workers from within the new site. Browsers are not caching the `sw.js` file which means it will be requested any time. This allows you to put destructive code in, which nukes the service worker from the user's browser.

```javascript
self.addEventListener('install', function(e) {

    self.skipWaiting();
});

self.addEventListener('activate', function(e) {
    self.registration.unregister()
        .then(function() {
            return self.clients.matchAll();
        })
        .then(function(clients) {
            clients.forEach(client => client.navigate(client.url))
        });
});
```

By ensuring this was present in my new site build at `https://jhankins.dev/sw.js`, I ensure that repeat visitors to my site get the newest non-Gatsby build.
