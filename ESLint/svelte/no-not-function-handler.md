Pattern: Use of non-function in event handler

Issue: -

## Description

This rule reports where you used not function value in event handlers.  
If you use a non-function value for the event handler, it event handler will not be called. It's almost always a mistake. You may have written a lot of unnecessary curly braces.

```svelte
<script>
  /* eslint svelte/no-not-function-handler: "error" */
  function foo() {
    /*  */
  }
  const bar = 42;
</script>

<!-- ✓ GOOD -->
<button on:click={foo} />
<button
  on:click={() => {
    /*  */
  }}
/>

<!-- ✗ BAD -->
<button on:click={{ foo }} />
<button on:click={bar} />
```

## :wrench: Options

Nothing.

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v0.5.0

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/no-not-function-handler.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/no-not-function-handler.ts)
