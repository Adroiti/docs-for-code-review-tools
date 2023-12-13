Pattern: Use of `{@html}`

Issue: -

## Description

This rule reports all uses of `{@html}` in order to reduce the risk of injecting potentially unsafe/unescaped HTML into the browser leading to Cross-Site Scripting (XSS) attacks.

```svelte
<script>
  /* eslint svelte/no-at-html-tags: "error" */
</script>

<!-- ✓ GOOD -->
{foo}

<!-- ✗ BAD -->
{@html foo}
```

## :wrench: Options

Nothing.

## :mute: When Not To Use It

If you are certain the content passed to `{@html}` is sanitized HTML you can disable this rule.

## :books: Further Reading

- [Svelte - Tutorial > 1. Introduction / HTML tags](https://svelte.dev/tutorial/html-tags)

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v0.0.1

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/no-at-html-tags.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/no-at-html-tags.ts)
