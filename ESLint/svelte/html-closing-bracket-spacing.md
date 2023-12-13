Pattern: Malformed space before tag's closing bracket

Issue: -

## Description

You can choose either two styles for spacing before closing bracket.

- always: `<div />`
- never: `<div/>`

```svelte
<script>
  /* eslint svelte/html-closing-bracket-spacing: "error" */
</script>

<!-- ✓ GOOD -->
<div />
<p>Hello</p>
<div
 >
</div>

<!-- ✗ BAD -->
<div/>
<p >Hello</p >
<div  >
</div >
```

## :wrench: Options

```json
{
  "svelte/html-closing-bracket-spacing": [
    "error",
    {
      "startTag": "never", // or "always" or "ignore"
      "endTag": "never", // or "always" or "ignore"
      "selfClosingTag": "always" // or "never" or "ignore"
    }
  ]
}
```

- `startTag` (`"never"` by default)... Spacing in start tags
- `endTag` (`"never"` by default)... Spacing in end tags
- `selfClosingTag` (`"always"` by default)... Spacing in self closing tags

Every option can be set to

- "always" (`<div />`)
- "never" (`<div/>`)
- "ignore" (either `<div />` or `<div/>`)

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v2.3.0

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/html-closing-bracket-spacing.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/html-closing-bracket-spacing.ts)
