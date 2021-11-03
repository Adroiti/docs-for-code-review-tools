Pattern: Missing `id` attribute for `next/script` component

Issue: -

## Description

`next/script` components with inline content require an `id` attribute to be defined to track and optimize the script.

### Possible Ways to Fix It

Add an `id` attribute to the `next/script` component.

```jsx
import Script from 'next/script'

export default function App({ Component, pageProps }) {
  return (
    <>
      <Script id="my-script">{`console.log('Hello world!');`}</Script>
      <Component {...pageProps} />
    </>
  )
}

```

## Further Reading

* [next.js - inline-script-id](https://nextjs.org/docs/messages/inline-script-id)