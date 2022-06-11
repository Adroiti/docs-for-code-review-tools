Pattern: Use of `next/script` inside `next/head`

Issue: -

## Description

The `next/script` component shouldn't be placed inside the `next/head` component.

#### Possible Ways to Fix It

Move the `<Script />` component outside of `<Head>...</Head>`

**Before**

```js
import Script from 'next/script'
import Head from 'next/head'

export default function Index() {
  return (
    <Head>
      <title>Next.js</title>
      <Script src="/my-script.js" />
    </Head>
  )
}
```

**After**

```js
import Script from 'next/script'
import Head from 'next/head'

export default function Index() {
  return (
    <>
      <Head>
        <title>Next.js</title>
      </Head>
      <Script src="/my-script.js" />
    </>
  )
}
```

## Further Reading

* [next.js - Script component inside Head component](https://nextjs.org/docs/messages/no-script-component-in-head-component)