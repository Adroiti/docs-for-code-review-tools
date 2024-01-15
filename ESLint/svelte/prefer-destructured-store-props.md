Pattern: Missing use of destructured store prop

Issue: -

## Description

This rule reports on directly accessing properties of a store containing an object in templates. These usages can instead be written as a reactive statement using destructuring to allow for more granular change-tracking and reduced redraws in the component.


```svelte
<script>
  /* eslint svelte/prefer-destructured-store-props: "error" */
  import store from './store.js';
  $: ({ foo } = $store);
</script>

<!-- ✓ GOOD -->
{foo}

<!-- ✗ BAD -->
{$store.foo}
```

## :wrench: Options

Nothing

## :heart: Compatibility

This rule was taken from [@tivac/eslint-plugin-svelte].  
This rule is compatible with `@tivac/svelte/store-prop-destructuring` rule.

[@tivac/eslint-plugin-svelte]: https://github.com/tivac/eslint-plugin-svelte/

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v2.10.0

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/prefer-destructured-store-props.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/prefer-destructured-store-props.ts)
