Pattern: Use of deprecated `destroyed`/`beforeDestroy` hooks

Issue: -

## Description

This rule reports use of deprecated `destroyed` and `beforeDestroy` lifecycle hooks. (in Vue.js 3.0.0+).

<eslint-code-block :rules="{'vue/no-deprecated-destroyed-lifecycle': ['error']}">

```vue
<script>
export default {
  /* ✓ GOOD */
  beforeMount () {},
  mounted () {},
  beforeUnmount () {},
  unmounted () {},

  /* ✗ BAD */
  beforeDestroy () {},
  destroyed () {}
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-deprecated-destroyed-lifecycle](https://eslint.vuejs.org/rules/no-deprecated-destroyed-lifecycle.html)
