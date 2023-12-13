Pattern: Use of the store itself as an operand

Issue: -

## Description

This rule disallow to use of the store itself as an operand.  
You should access the store value using the `$` prefix or the `get` function.

```svelte
<script>
  /* eslint svelte/require-store-reactive-access: "error" */
  import { writable, get } from 'svelte/store';
  const storeValue = writable('world');
  const color = writable('red');

  /* ✓ GOOD */
  $: message = `Hello ${$storeValue}`;

  /* ✗ BAD */
  $: message = `Hello ${storeValue}`;
</script>

<!-- ✓ GOOD -->
<p>{$storeValue}</p>
<p>{get(storeValue)}</p>

<p class={$storeValue} />
<p style:color={$color} />

<MyComponent prop="Hello {$storeValue}" />
<MyComponent bind:this={$storeValue} />
<MyComponent --style-props={$storeValue} />
<MyComponent {...$storeValue} />

<!-- ✗ BAD -->
<p>{storeValue}</p>

<p class={storeValue} />
<p style:color />

<MyComponent prop="Hello {storeValue}" />
<MyComponent bind:this={storeValue} />
<MyComponent --style-props={storeValue} />
<MyComponent {...storeValue} />
```

This rule checks the usage of store variables only if the store can be determined within a single file.  
However, when using `@typescript-eslint/parser` and full type information, this rule uses the type information to determine if the expression is a store.

```ts
// fileName: my-stores.ts
import { writable } from 'svelte/store';
export const storeValue = writable('hello');
```

```svelte
<script lang="ts">
  /* eslint svelte/require-store-reactive-access: "error" */
  import { storeValue } from './my-stores';
</script>

<!-- ✓ GOOD -->
<p>{$storeValue}</p>

<!-- ✗ BAD -->
<p>{storeValue}</p>
```

## :wrench: Options

Nothing.

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v2.12.0

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/require-store-reactive-access.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/require-store-reactive-access.ts)
