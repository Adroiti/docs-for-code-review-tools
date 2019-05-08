Pattern: Asynchronous action in computed property

Issue: -

## Description

This rule is aimed at preventing asynchronous methods from being called in computed properties. Computed properties should be synchronous. Asynchronous actions inside them may not work as expected and can lead to an unexpected behavior. If you need async computed properties you might want to consider using additional plug-in [vue-async-computed].

<eslint-code-block :rules="{'vue/no-async-in-computed-properties': ['error']}">

```vue
<script>
export default {
  computed: {
    /* ✓ GOOD */
    foo () {
      var bar = 0
      try {
        bar = bar / this.a
      } catch (e) {
        return 0
      } finally {
        return bar
      }
    },

    /* ✗ BAD */
    pro () {
      return Promise.all([new Promise((resolve, reject) => {})])
    },
    foo1: async function () {
      return await someFunc()
    },
    bar () {
      return fetch(url).then(response => {})
    },
    tim () {
      setTimeout(() => { }, 0)
    },
    inter () {
      setInterval(() => { }, 0)
    },
    anim () {
      requestAnimationFrame(() => {})
    }
  }
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-async-in-computed-properties](https://eslint.vuejs.org/rules/no-async-in-computed-properties.html)
