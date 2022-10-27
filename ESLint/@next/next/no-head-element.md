Pattern: Use of `<head>`

Issue: -

## Description

A `<head>` element was used to include page-level metadata, but this can cause unexpected behavior in a Next.js application. Use Next.js' built-in `next/head` component instead.

### Possible Ways to Fix It

Import and use the `<Head />` component:

```css
import Head from 'next/head'

function Index() {
  return (
    <>
      <Head>
        <title>My page title</title>
        <meta name="viewport" content="initial-scale=1.0, width=device-width" />
      </Head>
    </>
  )
}

export default Index
```

## Further Reading

* [next.js - No Head Element](https://nextjs.org/docs/messages/no-head-element)