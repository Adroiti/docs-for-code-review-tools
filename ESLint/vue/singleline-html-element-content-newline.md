Pattern: Missing line break for single-line element

Issue: -

## Description

This rule enforces a line break before and after the contents of a single-line element.

<eslint-code-block fix :rules="{'vue/singleline-html-element-content-newline': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div attr>
    content
  </div>
  
  <tr attr>
    <td>
      {{ data1 }}
    </td>
    <td>
      {{ data2 }}
    </td>
  </tr>
  
  <div attr>
    <!-- comment -->
  </div>
  
  <!-- ✗ BAD -->
  <div attr>content</div>
  
  <tr attr><td>{{ data1 }}</td><td>{{ data2 }}</td></tr>
  
  <div attr><!-- comment --></div>
</template>
```

</eslint-code-block>

## Options

```js
{
  "vue/singleline-html-element-content-newline": ["error", {
    "ignoreWhenNoAttributes": true,
    "ignoreWhenEmpty": true,
    "ignores": ["pre", "textarea", ...INLINE_ELEMENTS]
  }]
}
```

- `ignoreWhenNoAttributes` ... allows having contents in one line, when given element has no attributes.
    default `true`
- `ignoreWhenEmpty` ... disables reporting when element has no content.
    default `true`
- `ignores` ... the configuration for element names to ignore line breaks style.
    default `["pre", "textarea", ...INLINE_ELEMENTS]`.


### `"ignoreWhenNoAttributes": true`

<eslint-code-block fix :rules="{'vue/singleline-html-element-content-newline': ['error', {'ignoreWhenNoAttributes': true}]}">

```vue
<template>
  <!-- ✗ BAD -->
  <div attr>content</div>
  
  <tr attr><td>{{ data1 }}</td><td>{{ data2 }}</td></tr>
  
  <div attr><!-- comment --></div>
</template>
```

</eslint-code-block>

### `"ignoreWhenNoAttributes": false`

<eslint-code-block fix :rules="{'vue/singleline-html-element-content-newline': ['error', {'ignoreWhenNoAttributes': false}]}">

```vue
<template>
  <!-- ✗ BAD -->
  <div>content</div>
  
  <tr><td>{{ data1 }}</td><td>{{ data2 }}</td></tr>

  <div><!-- comment --></div>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - singleline-html-element-content-newline](https://eslint.vuejs.org/rules/singleline-html-element-content-newline.html)
