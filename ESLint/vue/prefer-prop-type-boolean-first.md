Pattern: `Boolean` not first in prop type

Issue: -

## Description

When declaring types of a property in component, we can use array style to accept multiple types.

When using components in template, we can use shorthand-style property if its value is `true`.

However, if a property allows `Boolean` or `String` and we use it with shorthand form in somewhere else,
different types order can introduce different behaviors:
If `Boolean` comes first, it will be `true`; if `String` comes first, it will be `""` (empty string).

<eslint-code-block :rules="{'vue/prefer-prop-type-boolean-first': ['error']}">

```vue
<script>
export default {
  props: {
    // ✓ GOOD
    a: Boolean,
    b: String,
    c: [Boolean, String],
    d: {
      type: [Boolean, String]
    },

    // ✗ BAD
    e: [String, Boolean],
    f: {
      type: [String, Boolean]
    }
  }
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - prefer-prop-type-boolean-first](https://eslint.vuejs.org/rules/prefer-prop-type-boolean-first.html)
