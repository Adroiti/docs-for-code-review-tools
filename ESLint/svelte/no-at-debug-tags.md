Pattern: Use of `{@debug}`

Issue: -

## Description

This rule reports all uses of `{@debug}`.

The `{@debug}` should be removed when you no longer need it after you use it for debugging.

```svelte
<script>
  /* eslint svelte/no-at-debug-tags: "error" */
</script>

<!-- ✗ BAD -->
{@debug user}
{@debug user1, user2, user3}
{@debug}
```

## :wrench: Options

Nothing.

## :books: Further Reading

- [Svelte - Tutorial > 18. Debugging / The @debug tags](https://svelte.dev/tutorial/debug)

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v0.0.1

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/no-at-debug-tags.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/no-at-debug-tags.ts)
