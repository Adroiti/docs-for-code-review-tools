Pattern: Missing `$slots` as function

Issue: -

## Description

This rule enforces the properties of `$slots` to be used as a function.  
`this.$slots.default` was an array of VNode in Vue.js 2.x, but changed to a function that returns an array of VNode in Vue.js 3.x.

<eslint-code-block :rules="{'vue/require-slots-as-functions': ['error']}">

```vue
<script>
export default {
  render(h) {
    /* ✓ GOOD */
    var children = this.$slots.default()
    var children = this.$slots.default && this.$slots.default()

    /* ✗ BAD */
    var children = [...this.$slots.default]
    var children = this.$slots.default.filter(test)
  }
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - require-slots-as-functions](https://eslint.vuejs.org/rules/require-slots-as-functions.html)
* [API - $slots](https://v3.vuejs.org/api/instance-properties.html#slots)
* [Vue RFCs - 0006-slots-unification](https://github.com/vuejs/rfcs/blob/master/active-rfcs/0006-slots-unification.md)
