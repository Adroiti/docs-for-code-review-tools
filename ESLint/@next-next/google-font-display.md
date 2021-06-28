Pattern: Missing use of `display`

Issue: -

## Description

For a Google Font, the `display` descriptor was either not assigned or set to `auto`, `fallback`, or `block`.

### Possible Ways to Fix It

For most cases, the best font display strategy for custom fonts is `optional`.

```jsx
import Head from 'next/head'

export default function IndexPage() {
  return (
    <div>
      <Head>
        <link
          href="https://fonts.googleapis.com/css2?family=Krona+One&display=optional"
          rel="stylesheet"
        />
      </Head>
    </div>
  )
}
```

Specifying `display=optional` minimizes the risk of invisible text or layout shift. If swapping to the custom font after it has loaded is important to you, then use `display=swap` instead.

## Further Reading

* [next.js - Google Font Display](https://nextjs.org/docs/messages/google-font-display)