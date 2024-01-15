Pattern: Missing use of shorthand syntax in directive

Issue: -

## Description

This rule enforces the use of the shorthand syntax in directives.

```svelte
<script>
  /* eslint svelte/shorthand-directive: "error" */
  let value = 'hello!'
  let active = true
  let color = 'red'
</script>

<!-- ✓ GOOD -->
<input bind:value>
<div class:active>...</div>
<div style:color>...</div>

<!-- ✗ BAD -->
<input bind:value={value}>
<div class:active={active}>...</div>
<div style:color={color}>...</div>
```

## :wrench: Options

```json
{
  "svelte/shorthand-directive": [
    "error",
    {
      "prefer": "always" // "never"
    }
  ]
}
```

- `prefer`
  - `"always"` ... Expects that the shorthand will be used whenever possible. This is default.
  - `"never"` ... Ensures that no shorthand is used in any directive.

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v0.24.0

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/shorthand-directive.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/shorthand-directive.ts)
