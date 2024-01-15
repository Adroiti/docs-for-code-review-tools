Pattern: Unused `svelte-ignore` comment

Issue: -

## Description

This rule warns unnecessary `svelte-ignore` comments.

```svelte
<script>
  /* eslint svelte/no-unused-svelte-ignore: "error" */
</script>

<!-- ✓ GOOD -->
<!-- svelte-ignore a11y-autofocus a11y-missing-attribute -->
<img src="https://example.com/img.png" autofocus />

<!-- ✗ BAD -->
<!-- svelte-ignore a11y-autofocus a11y-missing-attribute -->
<img src="https://example.com/img.png" alt="Foo" />
```

## :wrench: Options

Nothing.

## :books: Further Reading

- [Svelte - Docs > Comments](https://svelte.dev/docs#template-syntax-comments)

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v0.19.0

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/no-unused-svelte-ignore.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/no-unused-svelte-ignore.ts)
