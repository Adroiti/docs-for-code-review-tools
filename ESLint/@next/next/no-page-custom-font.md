Pattern: Use of custom page font

Issue: -

## Description

A custom font was added to a page and not with a custom `Document`. This only adds the font to the specific page and not to the entire application.

### Possible Ways to Fix It

Create the file `./pages/_document.js` and add the font to a custom Document:

```jsx
// pages/_document.js

import Document, { Html, Head, Main, NextScript } from 'next/document'

class MyDocument extends Document {
  render() {
    return (
      <Html>
        <Head>
          <link
            href="https://fonts.googleapis.com/css2?family=Inter&display=optional"
            rel="stylesheet"
          />
        </Head>
        <body>
          <Main />
          <NextScript />
        </body>
      </Html>
    )
  }
}

export default MyDocument
```

## Further Reading

* [next.js - No Page Custom Font](https://nextjs.org/docs/messages/no-page-custom-font)