Pattern: Malformed button type

Issue: -

## Description

This rule aims to warn if no type or an invalid type is used on a button type attribute.

```svelte
<script>
  /* eslint svelte/button-has-type: "error" */
</script>

<!-- ✓ GOOD -->
<button type="button">Hello World</button>
<button type="submit">Hello World</button>
<button type="reset">Hello World</button>

<!-- ✗ BAD -->
<button>Hello World</button>
<button type="">Hello World</button>
<button type="foo">Hello World</button>
```

## :wrench: Options

```json
{
  "svelte/button-has-type": [
    "error",
    {
      "button": true,
      "submit": true,
      "reset": true
    }
  ]
}
```

- `button` ... `<button type="button"></button>`
  - `true` (default) ... allow value `button`.
  - `false` ... disallow value `button`.
- `submit` ... `<button type="submit"></button>`
  - `true` (default) ... allow value `submit`.
  - `false` ... disallow value `submit`.
- `reset` ... `<button type="reset"></button>`
  - `true` (default) ... allow value `reset`.
  - `false` ... disallow value `reset`.

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v0.0.4

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/button-has-type.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/button-has-type.ts)
