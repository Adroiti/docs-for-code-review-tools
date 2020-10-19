Pattern: Passing multiple objects into array to class

Issue: -

## Description

This rule disallows to pass multiple objects into array to class.  

<eslint-code-block :rules="{'vue/no-multiple-objects-in-class': ['error']}">

```vue
<template>
  <div>
    <!-- ✓ GOOD -->
    <div :class="[{'foo': isFoo, 'bar': isBar}]" />

    <!-- ✗ BAD -->
    <div :class="[{'foo': isFoo}, {'bar': isBar}]" />
  </div>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-multiple-objects-in-class](https://eslint.vuejs.org/rules/no-multiple-objects-in-class.html)
