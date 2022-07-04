Pattern: `next/server` imported outside of `middleware.{js,ts}`

Issue: -

## Description

`next/server` was imported outside of `middleware.{js,ts}`.

### Possible Ways to Fix It

Only import and use `next/server` in a file located within the project root directory: `middleware.{js,ts}`.

```jsx
// middleware.ts

import type { NextFetchEvent, NextRequest } from 'next/server'

export function middleware(req: NextRequest, ev: NextFetchEvent) {
  return new Response('Hello, world!')
}

```

## Further Reading

* [next.js - No Server Import In Page](https://nextjs.org/docs/messages/no-server-import-in-page)