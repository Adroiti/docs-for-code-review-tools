Pattern: Missing default value for props

Issue: -

## Description

This rule requires default value to be set for each props that are not marked as `required` (except `Boolean` props).

<eslint-code-block :rules="{'vue/require-default-prop': ['error']}">

```vue
<script>
export default {
  props: {
    /* ✓ GOOD */
    a: {
      type: Number,
      required: true
    },
    b: {
      type: Number,
      default: 0
    },
    c: {
      type: Number,
      default: 0,
      required: false
    },
    d: {
      type: Boolean, // Boolean is the only type that doesn't require default
    },

    /* ✗ BAD */
    e: Number,
    f: [Number, String],
    g: [Boolean, Number],
    j: {
      type: Number
    },
    i: {
      type: Number,
      required: false
    }
  }
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - require-default-prop](https://eslint.vuejs.org/rules/require-default-prop.html)
