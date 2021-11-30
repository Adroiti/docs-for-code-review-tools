Pattern: Accessing computed property in `data()`

Issue: -

## Description

The computed property cannot be accessed in `data()` because is before initialization.

<eslint-code-block :rules="{'vue/no-computed-properties-in-data': ['error']}">

```vue
<script>
export default {
  data() {
    return  {
      /* ✗ BAD */
      bar: this.foo
    }
  },
  computed: {
    foo () {}
  }
}
</script>
```

</eslint-code-block>


## Further Reading

* [eslint-plugin-vue - no-computed-properties-in-data](https://eslint.vuejs.org/rules/no-computed-properties-in-data.html)
