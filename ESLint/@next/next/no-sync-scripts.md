Pattern: Use of synchronous script

Issue: -

## Description

A synchronous script was used which can impact your webpage's performance.

### Possible Ways to Fix It

#### Script component (experimental)

Use the Script component with the right loading strategy to defer loading of the script until necessary.

```jsx
import Script from 'next/script'

const Home = () => {
  return (
    <div class="container">
      <Script src="https://third-party-script.js"></Script>
      <div>Home Page</div>
    </div>
  )
}

export default Home
```

## Further Reading

* [next.js - No Sync Scripts](https://nextjs.org/docs/messages/no-sync-scripts)