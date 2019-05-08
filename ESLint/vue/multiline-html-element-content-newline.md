Pattern: Malformed newline for multi-line element

Issue: -

## Description

This rule enforces a line break before and after the contents of a multi-line element.

<eslint-code-block fix :rules="{'vue/multiline-html-element-content-newline': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div>
    multiline
    content
  </div>

  <pre>some
  content</pre>

  <div
    attr
  >
    multiline start tag
  </div>

  <table>
    <tr>
      <td>multiline</td>
      <td>children</td>
    </tr>
  </table>

  <div>
    <!-- multiline
         comment -->
  </div>

  <div
  >
  </div>

  <div attr>singleline element</div>

  <!-- ✗ BAD -->
  <div>multiline
    content</div>

  <div
    attr
  >multiline start tag</div>
  
  <table><tr><td>multiline</td>
    <td>children</td></tr></table>
  
  <div><!-- multiline
    comment --></div>

  <div
  ></div>
</template>
```

</eslint-code-block>

## Options

```js
{
    "vue/multiline-html-element-content-newline": ["error", {
        "ignoreWhenEmpty": true,
        "ignores": ["pre", "textarea", ...INLINE_ELEMENTS],
        "allowEmptyLines": false
    }]
}
```

- `ignoreWhenEmpty` ... disables reporting when element has no content.
    default `true`
- `ignores` ... the configuration for element names to ignore line breaks style.
    default `["pre", "textarea", ...INLINE_ELEMENTS]`.
- `allowEmptyLines` ... if `true`, it allows empty lines around content. If you want to disallow multiple empty lines, use [no-multiple-empty-lines] in combination.  
    default `false`

### `"ignores": ["VueComponent", "pre", "textarea"]`

<eslint-code-block fix :rules="{'vue/multiline-html-element-content-newline': ['error', { ignores: ['VueComponent', 'pre', 'textarea'] }]}">

```vue
<template>
  <!-- ✓ GOOD -->
  <VueComponent>multiline
  content</VueComponent>

  <pre>some
  content</pre>

  <VueComponent><span
    class="bold">For example,</span>
  Defines the Vue component that accepts preformatted text.</VueComponent>
</template>
```

</eslint-code-block>

### `"allowEmptyLines": true`

<eslint-code-block fix :rules="{'vue/multiline-html-element-content-newline': ['error', { allowEmptyLines: true }]}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div>
    content
  </div>
  <div>

    content

  </div>

  <!-- ✗ BAD -->
  <div>content
    content</div>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - multiline-html-element-content-newline](https://eslint.vuejs.org/rules/multiline-html-element-content-newline.html)
