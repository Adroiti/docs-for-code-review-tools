Pattern: Use of `<title>` within `Head` component

Issue: -

## Description

A `<title>` element was defined within the `Head` component imported from `next/document`, which should only be used for any `<head>` code that is common for all pages. Title tags should be defined at the page-level using `next/head`.

### Possible Ways to Fix It

Within a page or component, import and use `next/head` to define a page title:

```jsx
import Head from 'next/head'

export class Home {
  render() {
    return (
      <div>
        <Head>
          <title>My page title</title>
        </Head>
      </div>
    )
  }
}
```

## Further Reading

* [next.js - No Title in Document Head](https://nextjs.org/docs/messages/no-title-in-document-head)