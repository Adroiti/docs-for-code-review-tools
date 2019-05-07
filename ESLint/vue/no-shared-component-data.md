Pattern: no shared component data

Issue: -

## Description

When the value of `data` is an object, it’s shared across all instances of a component.

<eslint-code-block fix :rules="{'vue/no-shared-component-data': ['error']}">

```vue
<script>
/* ✓ GOOD */
Vue.component('some-comp', {
  data: function () {
    return {
      foo: 'bar'
    }
  }
})

export default {
  data () {
    return {
      foo: 'bar'
    }
  }
}
</script>
```

</eslint-code-block>

<eslint-code-block fix :rules="{'vue/no-shared-component-data': ['error']}">

```vue
<script>
/* ✗ BAD */
Vue.component('some-comp', {
  data: {
    foo: 'bar'
  }
})

export default {
  data: {
    foo: 'bar'
  }
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-shared-component-data](https://eslint.vuejs.org/rules/no-shared-component-data.html)
