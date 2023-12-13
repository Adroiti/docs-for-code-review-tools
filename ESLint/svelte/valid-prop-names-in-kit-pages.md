Pattern: Unexpected exported variables at `<script>`

Issue: -

## Description

This rule reports unexpected exported variables at `<script>`.
At SvelteKit v1.0.0-next.405, instead of having multiple props corresponding to the props returned from a load function, page components now have a single data prop.

<script>
  const config = {settings: {
    kit: {
      files: {
        routes: "",
      },
    },
  },
  }
</script>

<ESLintCodeBlock config="{config}">

```svelte
<script>
  /* eslint svelte/valid-prop-names-in-kit-pages: "error" */
  /** ✓ GOOD */
  export let data;
  export let errors;
  export let form;
  export let snapshot;
  // export let { data, errors } = { data: {}, errors: {} }

  /** ✗ BAD */
  export let foo;
  export let bar;
  export let { baz, qux } = data;
  export let { data: data2, errors: errors2 } = { data: {}, errors: {} };
</script>

{foo}, {bar}
```

## :wrench: Options

Nothing.

## :books: Further Reading

- [SvelteKit Migration Guide (v1.0.0-next.405)](https://github.com/sveltejs/kit/discussions/5774#discussioncomment-3292707)

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v2.12.0

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/valid-prop-names-in-kit-pages.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/valid-prop-names-in-kit-pages.ts)
