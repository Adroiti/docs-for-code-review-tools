Pattern: Use of script component inside `_document.js`

Issue: -

## Description

`_document.js` page only runs on the server and `next/script` has client-side functionality to ensure loading order.

### Possible Ways to Fix It

If you want a global script, instead use the `_app.js` page.

```jsx
import Script from 'next/script'

function MyApp({ Component, pageProps }) {
  return (
    <>
      <Script src="/my-script.js" />
      <Component {...pageProps} />
    </>
  )
}

export default MyApp
```

## Further Reading

* [next.js - Script component inside _document.js](https://nextjs.org/docs/messages/no-script-in-document-page)