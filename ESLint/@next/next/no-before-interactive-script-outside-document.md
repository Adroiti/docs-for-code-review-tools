Pattern: Use of `next/script` `beforeInteractive` strategy outside `next/_document`

Issue: -

## Description

You can't use the `next/script` component with the `beforeInteractive` strategy outside the `_document.js` page. That's because `beforeInteractive` strategy only works inside `_document.js` and is designed to load scripts that are needed by the entire site (i.e. the script will load when any page in the application has been loaded server-side).

### Possible Ways to Fix It

If you want a global script, move the script inside `_document.js` page.

```jsx
// In _document.js
import { Html, Head, Main, NextScript } from 'next/document'
import Script from 'next/script'

export default function Document() {
  return (
    <Html>
      <Head />
      <body>
        <Main />
        <NextScript />
        <Script
          src="https://cdnjs.cloudflare.com/ajax/libs/lodash.js/4.17.20/lodash.min.js"
          strategy="beforeInteractive"
        ></Script>
      </body>
    </Html>
  )
}

```

## Further Reading

* [next.js - beforeInteractive Script component outside _document.js](https://nextjs.org/docs/messages/no-before-interactive-script-outside-document)