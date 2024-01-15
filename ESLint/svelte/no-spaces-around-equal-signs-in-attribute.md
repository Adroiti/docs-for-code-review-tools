Pattern: Use of spaces around `=` in attribute

Issue: -

## Description

This rule disallows spaces around equal signs in attributes

```svelte
<script>
  /* eslint svelte/no-spaces-around-equal-signs-in-attribute: "error" */
</script>

<!-- ✓ GOOD -->
<div class=""/>
<p style="color: red;">hi</p>
<img src="img.png" alt="A photo of a very cute {animal}">

<!-- ✗ BAD -->
<div class = ""/>
<p style ="color: red;">hi</p>
<img src
    =
    "img.png" alt   = "A photo of a very cute {animal}">
```

## :wrench: Options

Nothing.

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v2.3.0

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/no-spaces-around-equal-signs-in-attribute.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/no-spaces-around-equal-signs-in-attribute.ts)
