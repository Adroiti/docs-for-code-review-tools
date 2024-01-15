Pattern: Missing use of shorthand syntax in attribute

Issue: -

## Description

This rule enforces the use of the shorthand syntax in attribute.

```svelte
<script>
  /* eslint svelte/shorthand-attribute: "error" */
</script>

<!-- ✓ GOOD -->
<button {disabled}>...</button>

<!-- ✗ BAD -->
<button disabled={disabled}>...</button>
```

## :wrench: Options

```json
{
  "svelte/shorthand-attribute": [
    "error",
    {
      "prefer": "always" // "never"
    }
  ]
}
```

- `prefer`
  - `"always"` ... Expects that the shorthand will be used whenever possible. This is default.
  - `"never"` ... Ensures that no shorthand is used in any attribute.

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v0.5.0

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/shorthand-attribute.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/shorthand-attribute.ts)
