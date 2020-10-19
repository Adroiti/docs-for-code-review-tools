Pattern: Use of empty component block

Issue: -

## Description

This rule disallows the `<template>` `<script>` `<style>` block to be empty.

<eslint-code-block :rules="{'vue/no-empty-component-block': ['error']}">

```vue
<!-- ✓ GOOD -->
<template>
  <p>foo</p>
</template>

<script>
  console.log('foo')
</script>

<style>
  p {
    display: inline;
  }
</style>

<template src="./template.html"></template>
<template src="./template.html" />

<script src="./script.js"></script>
<script src="./script.js" />

<style src="./style.css"></style>
<style src="./style.css" />


<!-- ✗ BAD -->
<template></template>
<template />
<template src="" />

<script></script>
<script />
<script src="" />

<style></style>
<style />
<style src="" />
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-empty-component-block](https://eslint.vuejs.org/rules/no-empty-component-block.html)
