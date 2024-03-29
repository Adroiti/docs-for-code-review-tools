Pattern: Unexpected exported `load` function in `*.svelte` module

Issue: -

## Description

This rule reports unexpected exported `load` function at `<script context="module">`.
At SvelteKit v1.0.0-next.405, `load` function has been moved into a separate file — `+page.js` for pages, `+layout.js` for layouts.

```svelte
<script context="module">
  /* eslint svelte/no-export-load-in-svelte-module-in-kit-pages: "error" */
  /* ✓ GOOD  */
  export function foo() {}
  export function bar() {}
  /* ✗ BAD  */
  export function load() {}
  // export const load = () => {}
</script>
```

## :wrench: Options

Nothing.

## :books: Further Reading

- [SvelteKit Migration Guide (v1.0.0-next.405)](https://github.com/sveltejs/kit/discussions/5774#discussioncomment-3292693)

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v2.12.0

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/no-export-load-in-svelte-module-in-kit-pages.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/no-export-load-in-svelte-module-in-kit-pages.ts)
