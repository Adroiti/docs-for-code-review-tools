Pattern: Inconsistent location for the first attribute

Issue: -

## Description

This rule aims to enforce a consistent location for the first attribute.

<eslint-code-block fix :rules="{'vue/first-attribute-linebreak': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <MyComponent lorem="1"/>
  <MyComponent lorem="1" ipsum="2"/>
  <MyComponent
    lorem="1"
    ipsum="2"
  />

  <!-- ✗ BAD -->
  <MyComponent lorem="1"
               ipsum="2"/>
</template>
```

</eslint-code-block>

## Options

```json
{
  "vue/first-attribute-linebreak": ["error", {
    "singleline": "ignore",
    "multiline": "below"
  }]
}
```

- `singleline` ... The location of the first attribute when the attributes on single line. Default is `"ignore"`.
  - `"below"` ... Requires a newline before the first attribute.
  - `"beside"` ... Disallows a newline before the first attribute.
  - `"ignore"` ... Ignores attribute checking.
- `multiline` ... The location of the first attribute when the attributes span multiple lines. Default is `"below"`.
  - `"below"` ... Requires a newline before the first attribute.
  - `"beside"` ... Disallows a newline before the first attribute.
  - `"ignore"` ... Ignores attribute checking.

### `"singleline": "beside"`

<eslint-code-block fix :rules="{'vue/first-attribute-linebreak': ['error', {singleline: 'beside'}]}">

```vue
<template>
  <!-- ✓ GOOD -->
  <MyComponent lorem="1"/>
  <MyComponent lorem="1" ipsum="2"/>

  <!-- ✗ BAD -->
  <MyComponent
    lorem="1"/>
  <MyComponent
    lorem="1" ipsum="2"
  />
</template>
```

</eslint-code-block>

### `"singleline": "below"`

<eslint-code-block fix :rules="{'vue/first-attribute-linebreak': ['error', {singleline: 'below'}]}">

```vue
<template>
  <!-- ✓ GOOD -->
  <MyComponent
    lorem="1"/>
  <MyComponent
    lorem="1" ipsum="2"
  />

  <!-- ✗ BAD -->
  <MyComponent lorem="1"/>
  <MyComponent lorem="1" ipsum="2"/>
</template>
```

</eslint-code-block>

### `"multiline": "beside"`

<eslint-code-block fix :rules="{'vue/first-attribute-linebreak': ['error', {multiline: 'beside'}]}">

```vue
<template>
  <!-- ✓ GOOD -->
  <MyComponent lorem="1"
               ipsum="2"/>
  <MyComponent :lorem="{
                 a: 1
               }"/>

  <!-- ✗ BAD -->
  <MyComponent
    lorem="1"
    ipsum="2"/>
  <MyComponent
    :lorem="{
      a: 1
    }"/>
</template>
```

</eslint-code-block>

### `"multiline": "below"`

<eslint-code-block fix :rules="{'vue/first-attribute-linebreak': ['error', {multiline: 'below'}]}">

```vue
<template>
  <!-- ✓ GOOD -->
  <MyComponent
    lorem="1"
    ipsum="2"/>
  <MyComponent
    :lorem="{
      a: 1
    }"/>

  <!-- ✗ BAD -->
  <MyComponent lorem="1"
               ipsum="2"/>
  <MyComponent :lorem="{
                 a: 1
               }"/>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - first-attribute-linebreak](https://eslint.vuejs.org/rules/first-attribute-linebreak.html)
