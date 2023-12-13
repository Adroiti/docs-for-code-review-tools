Pattern: Inconsistent variable and callback function names

Issue: -

## Description

This rule reports where variable names and callback function's argument names are different.
This is mainly a recommended rule to avoid implementation confusion.

```js
/* eslint svelte/derived-has-same-inputs-outputs: "error" */

import { derived } from 'svelte/store';

/* ✓ GOOD */
derived(a, ($a) => {});
derived(a, ($a, set) => {});
derived([a, b], ([$a, $b]) => {});

/* ✗ BAD */
derived(a, (b) => {});
derived(a, (b, set) => {});
derived([a, b], ([one, two]) => {});
```

## :wrench: Options

Nothing.

## :books: Further Reading

- [Svelte - Docs > RUN TIME > svelte/store > derived](https://svelte.dev/docs#run-time-svelte-store-derived)

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v2.8.0

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/derived-has-same-inputs-outputs.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/derived-has-same-inputs-outputs.ts)
