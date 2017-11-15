Pattern: Malformed space between `{}`

Issue: -

## Description

Requires or bans spaces between curly brace characters in JSX. Rule options: `["always", "never"]`.

Example of **incorrect** code (`always`):

```ts
const fail = <App someProp={test } />;
                           ~ [A space is required after {]
```

Example of **correct** code (`always`):

```ts
const pass = <App someProp={ test } />;
```