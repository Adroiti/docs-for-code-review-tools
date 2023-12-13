Pattern: Unnecessary function definition in reactive statement

Issue: -

## Description

This rule reports whenever a function is defined in a reactive statement. This isn't necessary, as each time the function is executed it'll already have access to the latest values necessary. Redefining the function in the reactive statement is just a waste of CPU cycles.

```svelte
<script>
  /* eslint svelte/no-reactive-functions: "error" */

  /* ✓ GOOD */
  const arrowFn = () => {
    /* ... */
  };
  const func = function () {
    /* ... */
  };

  /* ✗ BAD */
  $: arrowFn = () => {
    /* ... */
  };
  $: func = function () {
    /* ... */
  };
</script>
```

## :wrench: Options

Nothing

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v2.5.0

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/no-reactive-functions.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/no-reactive-functions.ts)
