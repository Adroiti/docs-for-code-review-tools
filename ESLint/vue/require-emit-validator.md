Pattern: Missing type definition for `emits`

Issue: -

## Description

This rule enforces that a `emits` statement contains type definition.

Declaring `emits` with types can bring better maintenance.
Even if using with TypeScript, this can provide better type inference when annotating parameters with types.

<eslint-code-block :rules="{'vue/require-emit-validator': ['error']}">

```vue
<script>
/* ✓ GOOD */
Vue.component('foo', {
  emits: {
    // Emit with arguments
    foo: (payload) => { /* validate payload */ },
    // Emit without parameters
    bar: () => true,
  }
})

/* ✗ BAD */
Vue.component('bar', {
  emits: ['foo']
})

Vue.component('baz', {
  emits: {
    foo: null,
  }
})
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - require-emit-validator](https://eslint.vuejs.org/rules/require-emit-validator.html)
