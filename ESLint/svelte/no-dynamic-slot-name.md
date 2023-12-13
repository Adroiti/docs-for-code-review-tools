Pattern: Use of dynamic `<slot>` name

Issue: -

## Description

This rule reports the dynamically specified `<slot>` name.  
Dynamic `<slot>` names are not allowed in Svelte, so you must use static names.

The auto-fix of this rule can be replaced with a static `<slot>` name if the expression given to the `<slot>` name is static and resolvable.

```svelte
<script>
  /* eslint svelte/no-dynamic-slot-name: "error" */
  const SLOT_NAME = 'bad';
</script>

<!-- ✓ GOOD -->
<slot name="good" />

<!-- ✗ BAD -->
<slot name={SLOT_NAME} />
```

## :wrench: Options

Nothing.

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v0.14.0

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/no-dynamic-slot-name.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/no-dynamic-slot-name.ts)
