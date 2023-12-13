Pattern: Unresolved Svelte warning

Issue: -

## Description

This rule uses Svelte compiler to check the source code.

```svelte
<script>
  /* eslint svelte/valid-compile: "error" */
  let src = 'tutorial/image.gif';
</script>

<!-- ✓ GOOD -->
<img {src} alt="Rick Astley dances." />

<!-- ✗ BAD -->
<img {src} />
```

Note that we exclude reports for some checks, such as `missing-declaration`, and `dynamic-slot-name`, which you can check with different ESLint rules.

## :wrench: Options

```json
{
  "svelte/valid-compile": [
    "error",
    {
      "ignoreWarnings": false
    }
  ]
}
```

- `ignoreWarnings` ... If set to `true`, ignores any warnings other than fatal errors reported by the svelte compiler.

```svelte
<script>
  /* eslint svelte/valid-compile: ["error", { ignoreWarnings: true }] */
  let src = 'tutorial/image.gif';
</script>

<!-- Ignore -->
<img {src} />
```

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v0.7.0

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/valid-compile.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/valid-compile.ts)
