Pattern: require direct export

Issue: -

## Description

This rule aims to require that the component object be directly exported.

<eslint-code-block :rules="{'vue/require-direct-export': ['error']}">

```vue
<script>
/* ✓ GOOD */
export default {
  name: 'ComponentA',
  data() {
    return {
      state: 1
    }
  }
}
</script>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/require-direct-export': ['error']}">

```vue
<script>
const ComponentA = {
  name: 'ComponentA',
  data() {
    return {
      state: 1
    }
  }
}

/* ✗ BAD */
export default ComponentA
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - require-direct-export](https://eslint.vuejs.org/rules/require-direct-export.html)
