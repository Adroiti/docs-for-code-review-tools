Pattern: html closing bracket spacing

Issue: -

## Description

This rule aims to enforce consistent spacing style before closing brackets `>` of tags.

<eslint-code-block fix :rules="{'vue/html-closing-bracket-spacing': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div>
  <div foo>
  <div foo="bar">
  </div>
  <div />
  <div foo />
  <div foo="bar" />

  <!-- ✗ BAD -->
  <div >
  <div foo >
  <div foo="bar" >
  </div >
  <div/>
  <div foo/>
  <div foo="bar"/>
</template>
```

</eslint-code-block>

## Options

```json
{
  "vue/html-closing-bracket-spacing": ["error", {
    "startTag": "always" | "never",
    "endTag": "always" | "never",
    "selfClosingTag": "always" | "never"
  }]
}
```

- `startTag` (`"always" | "never"`) ... Setting for the `>` of start tags (e.g. `<div>`). Default is `"never"`.
    - `"always"` ... requires one or more spaces.
    - `"never"` ... disallows spaces.
- `endTag` (`"always" | "never"`) ... Setting for the `>` of end tags (e.g. `</div>`). Default is `"never"`.
    - `"always"` ... requires one or more spaces.
    - `"never"` ... disallows spaces.
- `selfClosingTag` (`"always" | "never"`) ... Setting for the `/>` of self-closing tags (e.g. `<div/>`). Default is `"always"`.
    - `"always"` ... requires one or more spaces.
    - `"never"` ... disallows spaces.

### `"startTag": "always", "endTag": "always", "selfClosingTag": "always"`

<eslint-code-block fix :rules="{'vue/html-closing-bracket-spacing': ['error', {startTag: 'always', endTag: 'always', selfClosingTag: 'always' }]}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div >
  <div foo >
  <div foo="bar" >
  </div >
  <div />
  <div foo />
  <div foo="bar" />
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - html-closing-bracket-spacing](https://eslint.vuejs.org/rules/html-closing-bracket-spacing.html)
