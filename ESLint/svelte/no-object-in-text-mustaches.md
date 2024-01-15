Pattern: Use of object in text mustache interpolation

Issue: -

## Description

This rule disallows the use of objects in text mustache interpolation.  
When you use an object for text interpolation, it is drawn as `[object Object]`. It's almost always a mistake. You may have written a lot of unnecessary curly braces.

```svelte
<script>
  /* eslint svelte/no-object-in-text-mustaches: "error" */
</script>

<!-- ✓ GOOD -->
{foo}
<input class="{foo} bar" />
<MyComponent prop={{ foo }} />

<!-- ✗ BAD -->
{{ foo }}
<input class="{{ foo }} bar" />
```

## :wrench: Options

Nothing.

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v0.5.0

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/no-object-in-text-mustaches.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/no-object-in-text-mustaches.ts)
