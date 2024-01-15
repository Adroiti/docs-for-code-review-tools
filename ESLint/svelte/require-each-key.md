Pattern: Missing use of keyed `{#each}` block

Issue: -

## Description

This rule reports `{#each}` block without key.

```svelte
<script>
  /* eslint svelte/require-each-key: "error" */
</script>

<!-- ✓ GOOD -->
{#each things as thing (thing.id)}
  <Thing name={thing.name} />
{/each}

<!-- ✗ BAD -->
{#each things as thing}
  <Thing name={thing.name} />
{/each}
```

## :wrench: Options

Nothing.

## :books: Further Reading

- [Svelte - Tutorial > 4. Logic / Keyed each blocks](https://svelte.dev/tutorial/keyed-each-blocks)

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v2.28.0

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/require-each-key.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/require-each-key.ts)
