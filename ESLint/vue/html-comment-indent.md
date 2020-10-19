Pattern: Inconsistent HTML comment indent

Issue: -

## Description

This rule enforces a consistent indentation style in HTML comment (`<!-- ... -->`). The default style is 2 spaces.

<eslint-code-block fix :rules="{'vue/html-comment-indent': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <!--
    comment
  -->
  <!--
    comment
    comment
  -->
    <!--
      comment
    -->

  <!-- ✗ BAD -->
  <!--
  comment
      comment
  -->
  <!--
    comment
    -->
    <!--
    comment
  -->
</template>
```

</eslint-code-block>

## Options

```json
{
  "vue/html-comment-indent": ["error", type]
}
```

- `type` (`number | "tab"`) ... The type of indentation. Default is `2`. If this is a number, it's the number of spaces for one indent. If this is `"tab"`, it uses one tab for one indent.

### `2`

<eslint-code-block fix :rules="{'vue/html-comment-indent': ['error', 2]}">

```vue
<template>
  <!--
    ✓ GOOD
  -->

  <!--
   ✗ BAD
  -->
</template>
```

</eslint-code-block>

### `4`

<eslint-code-block fix :rules="{'vue/html-comment-indent': ['error', 4]}">

```vue
<template>
  <!--
      ✓ GOOD
  -->

  <!--
    ✗ BAD
  -->
</template>
```

</eslint-code-block>

### `0`

<eslint-code-block fix :rules="{'vue/html-comment-indent': ['error', 0]}">

```vue
<template>
  <!--
  ✓ GOOD
  -->

  <!--
    ✗ BAD
  -->
</template>
```

</eslint-code-block>

### `"tab"`

<eslint-code-block fix :rules="{'vue/html-comment-indent': ['error', 'tab']}">

```vue
<template>
  <!--
  	✓ GOOD
  -->

  <!--
    ✗ BAD
  -->
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - html-comment-indent](https://eslint.vuejs.org/rules/html-comment-indent.html)
