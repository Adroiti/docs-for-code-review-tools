Pattern: Use of duplicate polyfills

Issue: -

## Description

You are using Polyfill.io and including duplicate polyfills already shipped with Next.js. This increases page weight unnecessarily which can affect loading performance.

#### Possible Ways to Fix It

Remove all duplicate polyfills that are included with Polyfill.io. If you need to add polyfills but are not sure if Next.js already includes it, take a look at the list of [supported browsers and features](https://nextjs.org/docs/basic-features/supported-browsers-features) first.

## Further Reading

* [next.js - Duplicate Polyfills from Polyfill.io](https://nextjs.org/docs/messages/no-unwanted-polyfillio)