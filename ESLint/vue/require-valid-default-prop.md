Pattern: require valid default prop

Issue: -

## Description

This rule checks whether the default value of each prop is valid for the given type. It should report an error when default value for type `Array` or `Object` is not returned using function.

<eslint-code-block :rules="{'vue/require-valid-default-prop': ['error']}">

```vue
<script>
export default {
  props: {
    /* ✓ GOOD */
    // basic type check (`null` means accept any type)
    propA: Number,
    // multiple possible types
    propB: [String, Number],
    // a number with default value
    propD: {
      type: Number,
      default: 100
    },
    // object/array defaults should be returned from a factory function
    propE: {
      type: Object,
      default() {
        return { message: 'hello' }
      }
    },
    propF: {
      type: Array,
      default() {
        return []
      }
    },
    /* ✗ BAD */
    propA: {
      type: String,
      default: {}
    },
    propB: {
      type: String,
      default: []
    },
    propC: {
      type: Object,
      default: []
    },
    propD: {
      type: Array,
      default: []
    },
    propE: {
      type: Object,
      default: { message: 'hello' }
    }
  }
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - require-valid-default-prop](https://eslint.vuejs.org/rules/require-valid-default-prop.html)
