Pattern: Mutation of component prop

Issue: -

## Description

This rule reports mutation of component props.

<eslint-code-block :rules="{'vue/no-mutating-props': ['error']}">

```vue
<!-- ✗ BAD -->
<template>
  <div>
    <input v-model="value" @click="openModal">
  </div>
</template>
<script>
  export default {
    props: {
      value: {
        type: String,
        required: true
      }
    },
    methods: {
      openModal() {
        this.value = 'test'
      }
    }
  }
</script>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/no-mutating-props': ['error']}">

```vue
<!-- ✓ GOOD -->
<template>
  <div>
    <input :value="value" @input="$emit('input', $event.target.value)" @click="openModal">
  </div>
</template>
<script>
  export default {
    props: {
      value: {
        type: String,
        required: true
      }
    },
    methods: {
      openModal() {
        this.$emit('input', 'test')
      }
    }
  }
</script>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/no-mutating-props': ['error']}">

```vue
<script>
  export default {
    setup (props) {
      // ✗ BAD
      props.value = 'test'
    }
  }
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-mutating-props](https://eslint.vuejs.org/rules/no-mutating-props.html)
* [Style guide - Implicit parent-child communication](https://v3.vuejs.org/style-guide/#implicit-parent-child-communication-use-with-caution)
* [Vue - Prop Mutation - deprecated](https://vuejs.org/v2/guide/migration.html#Prop-Mutation-deprecated)
