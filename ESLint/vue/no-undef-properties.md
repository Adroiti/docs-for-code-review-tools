Pattern: Use of undefined property

Issue: -

## Description

Warns of using undefined properties.  This rule can help you locate potential errors resulting from misspellings property names, and implicitly added properties.


<eslint-code-block :rules="{'vue/no-undef-properties': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div>{{ name }}: {{ count }}</div>
  <!-- ✗ BAD -->
  <div>{{ label }}: {{ cnt }}</div>
</template>
<script setup>
const prop = defineProps(['name', 'def'])
let count = 0

/* ✓ GOOD */
watch(() => prop.def, () => console.log('Updated!'))

/* ✗ BAD */
watch(() => prop.undef, () => console.log('Updated!'))
</script>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/no-undef-properties': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div>{{ name }}: {{ count }}</div>
  <!-- ✗ BAD -->
  <div>{{ label }}: {{ cnt }}</div>
</template>
<script>
  export default {
    props: ['name'],
    data () {
      return {
        count: 0
      }
    },
    methods: {
      click() {
        /* ✓ GOOD */
        this.count++

        /* ✗ BAD */
        this.cnt++
      }
    }
  }
</script>
```

</eslint-code-block>

## Options

```json
{
  "vue/no-undef-properties": ["error", {
    "ignores": ["/^\\$/"]
  }]
}
```

- `ignores` (`string[]`) ... An array of property names or patterns that have already been defined property, or property to ignore from the check. Default is `["/^\\$/"]`.

### `"ignores": ["/^\\$/"]` (default)

<eslint-code-block :rules="{'vue/no-undef-properties': ['error', {ignores: ['/^\\$/']}]}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div>{{ $t('foo') }}</div>
</template>
<script>
  export default {
    mounted() {
      /* ✓ GOOD */
      const hash = this.$route.hash
    }
  }
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-undef-properties](https://eslint.vuejs.org/rules/no-undef-properties.html)
