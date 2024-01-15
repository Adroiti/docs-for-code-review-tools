Pattern: Inconsistent location of first attribute

Issue: -

## Description

This rule aims to enforce a consistent location for the first attribute.

```svelte
<script>
  /* eslint svelte/first-attribute-linebreak: "error" */
</script>

<!-- ✓ GOOD -->
<input type="checkbox" />
<button
  type="button"
  on:click={click} />
<button type="button" on:click={click} />

<!-- ✗ BAD -->
<input
  type="checkbox" />
<button type="button"
  on:click={click} />
<button
  type="button" on:click={click} />
```

## :wrench: Options

```json
{
  "svelte/first-attribute-linebreak": [
    "error",
    {
      "multiline": "below", // or "beside"
      "singleline": "beside" // "below"
    }
  ]
}
```

- `multiline` ... The location of the first attribute when the attributes span multiple lines. Default is `"below"`.
  - `"below"` ... Requires a newline before the first attribute.
  - `"beside"` ... Disallows a newline before the first attribute.
- `singleline` ... The location of the first attribute when the attributes on single line. Default is `"beside"`.
  - `"below"` ... Requires a newline before the first attribute.
  - `"beside"` ... Disallows a newline before the first attribute.

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v0.6.0

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/first-attribute-linebreak.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/first-attribute-linebreak.ts)
