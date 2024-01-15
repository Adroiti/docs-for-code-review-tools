Pattern: Too many attributes per line

Issue: -

## Description

Limits the maximum number of attributes/directives per line to improve readability.

This rule aims to enforce a number of attributes per line in templates.
It checks all the elements in a template and verifies that the number of attributes per line does not exceed the defined maximum.
An attribute is considered to be in a new line when there is a line break between two attributes.

There is a configurable number of attributes that are acceptable in one-line case (default 1), as well as how many attributes are acceptable per line in multi-line case (default 1).

```svelte
<script>
  /* eslint svelte/max-attributes-per-line: "error" */
</script>

<!-- ✓ GOOD -->
<input
  type="text"
  bind:value={text}
  {maxlength}
  {...attrs}
  readonly
  size="20"
/>
<button
  type="button"
  on:click={click}
  {maxlength}
  {...attrs}
  disabled
  data-my-data="foo"
/>

<!-- ✗ BAD -->
<input type="text" bind:value={text} {maxlength} {...attrs} readonly />
<button type="button" on:click={click} {maxlength} {...attrs}> CLICK ME! </button>
```

## :wrench: Options

```json
{
  "svelte/max-attributes-per-line": [
    "error",
    {
      "multiline": 1,
      "singleline": 1
    }
  ]
}
```

- `multiline` ... The number of maximum attributes per line when the opening tag is in multiple lines. Default is `1`.
- `singleline` ... The number of maximum attributes per line when the opening tag is in a single line. Default is `1`.

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v0.2.0

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/max-attributes-per-line.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/max-attributes-per-line.ts)
