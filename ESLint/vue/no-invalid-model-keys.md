Pattern: Use of invalid model key

Issue: -

## Description

This rule is aimed at preventing invalid keys in model option.

<eslint-code-block :rules="{'vue/no-invalid-model-keys': ['error']}">

```vue
<script>
/* ✓ GOOD */
export default {
  model: {
    prop: 'list',
  }
}
</script>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/no-invalid-model-keys': ['error']}">

```vue
<script>
/* ✓ GOOD */
export default {
  model: {
    event: 'update'
  }
}
</script>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/no-invalid-model-keys': ['error']}">

```vue
<script>
/* ✓ GOOD */
export default {
  model: {
    prop: 'list',
    event: 'update'
  }
}
</script>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/no-invalid-model-keys': ['error']}">

```vue
<script>
/* ✗ BAD */
export default {
  model: {
    prop: 'list',
    events: 'update'
  }
}
</script>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/no-invalid-model-keys': ['error']}">

```vue
<script>
/* ✗ BAD */
export default {
  model: {
    props: 'list',
    events: 'update'
  }
}
</script>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/no-invalid-model-keys': ['error']}">

```vue
<script>
/* ✗ BAD */
export default {
  model: {
    name: 'checked',
    props: 'list',
    event: 'update'
  }
}
</script>
```

</eslint-code-block>


## Further Reading

* [eslint-plugin-vue - no-invalid-model-keys](https://eslint.vuejs.org/rules/no-invalid-model-keys.html)
