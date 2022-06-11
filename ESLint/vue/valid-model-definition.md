Pattern: Invalid model definition

Issue: -

## Description

This rule is aimed at preventing invalid keys in model option.

<eslint-code-block :rules="{'vue/valid-model-definition': ['error']}">

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

<eslint-code-block :rules="{'vue/valid-model-definition': ['error']}">

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

<eslint-code-block :rules="{'vue/valid-model-definition': ['error']}">

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

<eslint-code-block :rules="{'vue/valid-model-definition': ['error']}">

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

<eslint-code-block :rules="{'vue/valid-model-definition': ['error']}">

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

<eslint-code-block :rules="{'vue/valid-model-definition': ['error']}">

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

* [eslint-plugin-vue - valid-model-definition](https://eslint.vuejs.org/rules/valid-model-definition.html)
