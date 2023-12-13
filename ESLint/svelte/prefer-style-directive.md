Pattern: Missing use of style directive

Issue: -

## Description

This rule aims to replace a style attribute with the style directive.

Style directive were added in Svelte v3.46.

```svelte
<script>
  /* eslint svelte/prefer-style-directive: "error" */
  let color = "red"
</script>

<!-- ✓ GOOD -->
<div style:color={color}>...</div>
<div
  style:position="absolute"
  style:top={position === "absolute" ? "20px" : null}
  style:pointer-events={pointerEvents ? null : "none"}
/>

<!-- ✗ BAD -->
<div style="color: {color};">...</div>
<div
  style="
    position: {position};
    {position === 'absolute' ? 'top: 20px;' : ''}
    {pointerEvents === false ? 'pointer-events:none;' : ''}
  "
/>
```

You cannot enforce this style by using [prettier-plugin-svelte]. That is, this rule does not conflict with [prettier-plugin-svelte] and can be used with [prettier-plugin-svelte].

[prettier-plugin-svelte]: https://github.com/sveltejs/prettier-plugin-svelte

## :wrench: Options

Nothing.

## :books: Further Reading

- [Svelte - Docs > style:property](https://svelte.dev/docs#template-syntax-element-directives-style-property)

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v0.22.0

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/prefer-style-directive.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/prefer-style-directive.ts)
