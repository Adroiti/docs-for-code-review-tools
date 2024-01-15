Pattern: Unnecessary literal in reactive statement

Issue: -

## Description

This rule reports on any assignment of a static, unchanging value within a reactive statement because it's not necessary.

```svelte
<script>
  /* eslint svelte/no-reactive-literals: "error" */
  /* ✓ GOOD */
  let foo = 'bar';

  /* ✗ BAD */
  $: foo = 'bar';
</script>
```

## :wrench: Options

Nothing.

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v2.4.0

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/no-reactive-literals.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/no-reactive-literals.ts)
