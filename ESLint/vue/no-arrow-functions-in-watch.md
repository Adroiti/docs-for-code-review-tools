Pattern: Use of arrow functions to define watcher

Issue: -

## Description

This rules disallows using arrow functions to defined watcher. The reason is arrow functions bind the parent context, so `this` will not be the Vue instance as you expect.

<eslint-code-block :rules="{'vue/no-arrow-functions-in-watch': ['error']}">

```vue
<script>
export default {
  watch: {
    /* ✓ GOOD */
    a: function (val, oldVal) {
      console.log('new: %s, old: %s', val, oldVal)
    },
    b: 'someMethod',
    c: {
      handler: function (val, oldVal) { /* ... */ },
      deep: true
    },
    d: {
      handler: 'someMethod',
      immediate: true
    },
    e: [
      'handle1',
      function handle2 (val, oldVal) { /* ... */ },
      {
        handler: function handle3 (val, oldVal) { /* ... */ },
        /* ... */
      }
    ],
    'e.f': function (val, oldVal) { /* ... */ },

    /* ✗ BAD */
    foo: (val, oldVal) => {
      console.log('new: %s, old: %s', val, oldVal)
    }
  }
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-arrow-functions-in-watch](https://eslint.vuejs.org/rules/no-arrow-functions-in-watch.html)
