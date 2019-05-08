Pattern: Malformed spacing for mustache interpolation

Issue: -

## Description

This rule aims at enforcing unified spacing in mustache interpolations.

<eslint-code-block fix :rules="{'vue/mustache-interpolation-spacing': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div>{{ text }}</div>
  <div>{{   text   }}</div><!-- Use vue/no-multi-spaces rule to disallow multiple spaces. -->

  <!-- ✗ BAD -->
  <div>{{text}}</div>
</template>
```

</eslint-code-block>

## Options

```json
{
  "vue/mustache-interpolation-spacing": ["error", "always" | "never"]
}
```

- `"always"` (default) ... Expect one space between expression and curly brackets.
- `"never"` ... Expect no spaces between expression and curly brackets.

### `"never"`

<eslint-code-block fix :rules="{'vue/mustache-interpolation-spacing': ['error', 'never']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div>{{text}}</div>

  <!-- ✗ BAD -->
  <div>{{   text   }}</div>
  <div>{{ text }}</div>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - mustache-interpolation-spacing](https://eslint.vuejs.org/rules/mustache-interpolation-spacing.html)
