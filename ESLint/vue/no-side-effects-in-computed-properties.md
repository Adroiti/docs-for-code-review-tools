Pattern: Side effect in computed property

Issue: -

## Description

This rule is aimed at preventing the code which makes side effects in computed properties.

It is considered a very bad practice to introduce side effects inside computed properties. It makes the code not predictable and hard to understand.

<eslint-code-block :rules="{'vue/no-side-effects-in-computed-properties': ['error']}">

```vue
<script>
/* ✓ GOOD */
export default {
  computed: {
    fullName () {
      return `${this.firstName} ${this.lastName}`
    },
    reversedArray () {
      return this.array.slice(0).reverse() // .slice makes a copy of the array, instead of mutating the orginal
    }
  }
}
</script>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/no-side-effects-in-computed-properties': ['error']}">

```vue
<script>
/* ✗ BAD */
export default {
  computed: {
    fullName () {
      this.firstName = 'lorem' // <- side effect
      return `${this.firstName} ${this.lastName}`
    },
    reversedArray () {
      return this.array.reverse() // <- side effect - orginal array is being mutated
    }
  }
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-side-effects-in-computed-properties](https://eslint.vuejs.org/rules/no-side-effects-in-computed-properties.html)
