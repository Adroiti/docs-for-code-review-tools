Pattern: Use of restricted HTML element

Issue: -

## Description

This rule reports to usage of restricted HTML elements.

```svelte
<script>
  /* eslint svelte/no-restricted-html-elements: ["error", "h1", "h2", "h3", "h4", "h5", "h6"] */
</script>

<!-- ✓ GOOD -->
<div>
  <p>Hi!</p>
</div>

<!-- ✗ BAD -->
<h1>foo</h1>

<div>
  <h2>bar</h2>
</div>
```

---

```svelte
<script>
  /* eslint svelte/no-restricted-html-elements: ["error", { "elements": ["marquee"], "message": "Do not use deprecated HTML tags" }] */
</script>

<!-- ✓ GOOD -->
<div>
  <p>Hi!</p>
</div>

<!-- ✗ BAD -->
<marquee>foo</marquee>

<div>
  <marquee>bar</marquee>
</div>
```

## :wrench: Options

This rule takes a list of strings, where each string is an HTML element name to be restricted:

```json
{
  "svelte/no-restricted-html-elements": ["error", "h1", "h2", "h3", "h4", "h5", "h6"]
}
```

Alternatively, the rule also accepts objects.

```json
{
  "svelte/no-restricted-html-elements": [
    "error",
    {
      "elements": ["h1", "h2", "h3", "h4", "h5", "h6"],
      "message": "Prefer use of our custom <Heading /> component"
    },
    {
      "elements": ["marquee"],
      "message": "Do not use deprecated HTML tags"
    }
  ]
}
```

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v2.31.0

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/no-restricted-html-elements.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/no-restricted-html-elements.ts)
