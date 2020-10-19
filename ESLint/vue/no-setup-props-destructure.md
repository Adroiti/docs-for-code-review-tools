Pattern: Destructuring of `props` passed to `setup`

Issue: -

## Description

This rule reports the destructuring of `props` passed to `setup` causing the value to lose reactivity.

<eslint-code-block :rules="{'vue/no-setup-props-destructure': ['error']}">

```vue
<script>
export default {
  /* ✓ GOOD */
  setup(props) {
    watch(() => {
      console.log(props.count)
    })

    return () => {
      return h('div', props.count)
    }
  }
}
</script>
```

</eslint-code-block>

Destructuring the `props` passed to `setup` will cause the value to lose reactivity.

<eslint-code-block :rules="{'vue/no-setup-props-destructure': ['error']}">

```vue
<script>
export default {
  /* ✗ BAD */
  setup({ count }) {
    watch(() => {
      console.log(count) // not going to detect changes
    })

    return () => {
      return h('div', count) // not going to update
    }
  }
}
</script>
```

</eslint-code-block>

Also, destructuring in root scope of `setup()` should error, but ok inside nested callbacks or returned render functions:

<eslint-code-block :rules="{'vue/no-setup-props-destructure': ['error']}">

```vue
<script>
export default {
  setup(props) {
    /* ✗ BAD */
    const { count } = props

    watch(() => {
      /* ✓ GOOD */
      const { count } = props
      console.log(count)
    })

    return () => {
      /* ✓ GOOD */
      const { count } = props
      return h('div', count)
    }
  }
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-setup-props-destructure](https://eslint.vuejs.org/rules/no-setup-props-destructure.html)
* [Guide - Composition API - Setup](https://v3.vuejs.org/guide/composition-api-setup.html)
* [Vue RFCs - 0013-composition-api](https://github.com/vuejs/rfcs/blob/master/active-rfcs/0013-composition-api.md)
