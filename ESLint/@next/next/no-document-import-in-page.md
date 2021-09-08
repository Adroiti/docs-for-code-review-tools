Pattern: Use of `next/document` outside of `pages/_document.js`

Issue: -

## Description

`next/document` was imported in a page outside of `pages/_document.js` (or `pages/_document.tsx` if you are using TypeScript). This can cause unexpected issues in your application.

### Possible Ways to Fix It

Only import and use `next/document` within `pages/_document.js` (or `pages/_document.tsx`) to override the default `Document` component:

```jsx
// pages/_document.js
import Document, { Html, Head, Main, NextScript } from 'next/document'

class MyDocument extends Document {
  //...
}

export default MyDocument
```

## Further Reading

* [next.js - No Document Import in Page](https://nextjs.org/docs/messages/no-document-import-in-page)