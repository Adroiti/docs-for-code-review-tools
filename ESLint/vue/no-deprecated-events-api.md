Pattern: Use of deprecated events API

Issue: -

## Description

This rule reports use of deprecated `$on`, `$off` `$once` API. (in Vue.js 3.0.0+).

<eslint-code-block :rules="{'vue/no-deprecated-events-api': ['error']}">

```vue
<script>
/* ✗ BAD */
export default {
  mounted () {
    this.$on('start', function(args) {
      console.log('start')
    })
    this.$emit('start')
  }
}
</script>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/no-deprecated-events-api': ['error']}">

```vue
<script>
/* ✓ GOOD */
import mitt from 'mitt'
const emitter = mitt()
export default {
  mounted () {
    emitter.on('start', function(args) {
      console.log('start')
    })
    emitter.emit('start')
  }
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-deprecated-events-api](https://eslint.vuejs.org/rules/no-deprecated-events-api.html)
* [Migration Guide - Events API](https://v3.vuejs.org/guide/migration/events-api.html)
* [Vue RFCs - 0020-events-api-change](https://github.com/vuejs/rfcs/blob/master/active-rfcs/0020-events-api-change.md).
