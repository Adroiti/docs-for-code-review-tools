Pattern: Inconsistent spacing after `<!--` and before `-->`

Issue: -

## Description

This rule will enforce consistency of spacing after the start of a comment `<!--` and before the end of a comment `-->`.

```svelte
<script>
  /* eslint svelte/spaced-html-comment: "error" */
</script>

<!-- ✓ GOOD -->

<!--✗ BAD-->
```

## :wrench: Options

```json
{
  "svelte/spaced-html-comment": [
    "error",
    "always" // or "never"
  ]
}
```

- `"always"` ... There must be at least one whitespace after `<!--` and before `-->`.
- `"never"` ... There should be no leading or trailing whitespace. There should be no whitespace following.

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v0.0.1

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/spaced-html-comment.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/spaced-html-comment.ts)
