Pattern: Client component as async function

Issue: -

## Description

Client components should not be async functions.

It's too easy for a single prop to flow through the component and invalidate its memoization, triggering the microtask dance. It's not so much that it introduces new performance caveats, but it makes all the performance caveats described above much more likely.

### Possible Ways to Fix It

1. Remove the `async` keyword from the client component function declaration, or
2. Convert the client component to a server component

## Further Reading

* [next.js - No async client component](https://nextjs.org/docs/messages/no-async-client-component)