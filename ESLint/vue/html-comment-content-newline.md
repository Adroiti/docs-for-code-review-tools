Pattern: Inconsistent HTML comment content newline

Issue: -

## Description

This rule will enforce consistency of line break after the `<!--` and before the `-->` of comment. It also provides several exceptions for various documentation styles.

<eslint-code-block fix :rules="{'vue/html-comment-content-newline': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <!-- singleline comment -->
  <!--
    multiline
    comment
  -->

  <!--
    ✗ BAD
  -->
  <!--
    singleline comment
  -->
  <!-- multiline
    comment -->
</template>
```

</eslint-code-block>

## Options

```json
{
  "vue/html-comment-content-newline": ["error",
    {
      "singleline": "always" | "never" | "ignore",
      "multiline": "always" | "never" | "ignore",
    },
    {
      "exceptions": []
    }
  ]
}
```

- The first option is either an object with `"singleline"` and `"multiline"` keys.
    - `singleline` ... the configuration for single-line comments.
        - `"never"` (default) ... disallow line breaks after the `<!--` and before the `-->`.
        - `"always"` ... require one line break after the `<!--` and before the `-->`.
    - `multiline` ... the configuration for multiline comments.
        - `"never"` ... disallow line breaks after the `<!--` and before the `-->`.
        - `"always"` (default) ... require one line break after the `<!--` and before the `-->`.

    You can also set the same value for both `singleline` and `multiline` by specifies a string.

- This rule can also take a 2nd option, an object with the following key: `"exceptions"`.
    - The `"exceptions"` value is an array of string patterns which are considered exceptions to the rule.

    ```json
    "vue/html-comment-content-newline": ["error", { ... }, { "exceptions": ["*"] }]
    ```

### `"always"`

<eslint-code-block fix :rules="{'vue/html-comment-content-newline': ['error', { 'singleline': 'always', 'multiline': 'always' }]}">

```vue
<template>
  <!--
    ✓ GOOD
  -->
  <!--
    singleline comment
  -->
  <!--
    multiline
    comment
  -->

  <!-- ✗ BAD -->
  <!-- singleline comment -->
  <!-- multiline
    comment -->
</template>
```

</eslint-code-block>

### `"never"`

<eslint-code-block fix :rules="{'vue/html-comment-content-newline': ['error', { 'singleline': 'never', 'multiline': 'never' }]}">

```vue
<template>
  <!-- ✓ GOOD -->
  <!-- singleline comment -->
  <!-- multiline
    comment -->

  <!--
    ✗ BAD
  -->
  <!--
    singleline comment
  -->
  <!--
    multiline
    comment
  -->
</template>
```

</eslint-code-block>

### `{"singleline": "always", "multiline": "ignore"}`

<eslint-code-block fix :rules="{'vue/html-comment-content-newline': ['error', { 'singleline': 'always', 'multiline': 'ignore' }]}">

```vue
<template>
  <!--
    ✓ GOOD
  -->
  <!--
    singleline comment
  -->
  <!--

    singleline comment

  -->
  <!-- multiline
    comment -->
  <!--
    multiline
    comment
  -->
  <!--

    multiline
    comment

  -->

  <!-- ✗ BAD -->
  <!-- singleline comment -->
  <!--     singleline comment     -->
</template>
```

</eslint-code-block>


### `{"singleline": "ignore", "multiline": "always"}`

<eslint-code-block fix :rules="{'vue/html-comment-content-newline': ['error', { 'singleline': 'ignore', 'multiline': 'always' }]}">

```vue
<template>
  <!-- ✓ GOOD -->
  <!--
    multiline
    comment
  -->
  <!--

    multiline
    comment

  -->
  <!-- singleline comment -->
  <!--
    singleline comment
  -->
  <!--

    singleline comment

  -->

  <!-- ✗ BAD -->
  <!-- multiline
    comment -->
</template>
```

</eslint-code-block>

### `"always", { "exceptions": ["*"] }`

<eslint-code-block fix :rules="{'vue/html-comment-content-newline': ['error', 'always', { 'exceptions': ['*'] }]}">

```vue
<template>
  <!--*******
    ✓ GOOD
    *******-->
  <!--*******
    comment
    *******-->

  <!--******* ✗ BAD *******-->
  <!--******* multiline
    comment *******-->
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - html-comment-content-newline](https://eslint.vuejs.org/rules/html-comment-content-newline.html)
