Pattern: Missing type definition in `props`

Issue: -

## Description

This rule enforces that a `props` statement contains type definition.

In committed code, prop definitions should always be as detailed as possible, specifying at least type(s).

<eslint-code-block :rules="{'vue/require-prop-types': ['error']}">

```vue
<script>
/* ✓ GOOD */
Vue.component('foo', {
  props: {
    // Without options, just type reference
    foo: String,
    // With options with type field
    bar: {
      type: String,
      required: true,
    },
    // With options without type field but with validator field
    baz: {
      required: true,
      validator: function (value) {
        return (
          value === null ||
          Array.isArray(value) && value.length > 0
        )
      }
    }
  }
})

/* ✗ BAD */
Vue.component('bar', {
  props: ['foo']
})

Vue.component('baz', {
  props: {
    foo: {},
  }
})
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - require-prop-types](https://eslint.vuejs.org/rules/require-prop-types.html)
