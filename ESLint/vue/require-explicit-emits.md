Pattern: Missing explicit `emits`

Issue: -

## Description

This rule reports event triggers not declared with the `emits` option. (The `emits` option is a new in Vue.js 3.0.0+)

Explicit `emits` declaration serves as self-documenting code. This can be useful for other developers to instantly understand what events the component is supposed to emit.

Also,  with attribute fallthrough changes in Vue.js 3.0.0+, `v-on` listeners on components will fallthrough as native listeners by default. Declare it as a component-only event in `emits` to avoid unnecessary registration of native listeners.

<eslint-code-block :rules="{'vue/require-explicit-emits': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div @click="$emit('good')"/>
  <!-- ✗ BAD -->
  <div @click="$emit('bad')"/>
</template>
<script>
export default {
  emits: ['good']
}
</script>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/require-explicit-emits': ['error']}">

```vue
<script>
export default {
  emits: ['good'],
  methods: {
    foo () {
      // ✓ GOOD
      this.$emit('good')
      // ✗ BAD
      this.$emit('bad')
    }
  }
}
</script>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/require-explicit-emits': ['error']}">

```vue
<script>
export default {
  emits: ['good'],
  setup (props, context) {
    // ✓ GOOD
    context.emit('good')
    // ✗ BAD
    context.emit('bad')
  }
}
</script>
```

</eslint-code-block>

## Options

```json
{
  "vue/require-explicit-emits": ["error", {
    "allowProps": false
  }]
}
```

- `"allowProps"` ... If `true`, allow event names defined in `props`. default `false`

### `"allowProps": true`

<eslint-code-block :rules="{'vue/require-explicit-emits': ['error', {allowProps: true}]}">

```vue
<script>
export default {
  props: ['onGood', 'bad'],
  methods: {
    foo () {
      // ✓ GOOD
      this.$emit('good')
      // ✗ BAD
      this.$emit('bad')
    }
  }
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - require-explicit-emits](https://eslint.vuejs.org/rules/require-explicit-emits.html)
* [Guide - Custom Events / Defining Custom Events](https://v3.vuejs.org/guide/component-custom-events.html#defining-custom-events)
* [Vue RFCs - 0030-emits-option](https://github.com/vuejs/rfcs/blob/master/active-rfcs/0030-emits-option.md)

