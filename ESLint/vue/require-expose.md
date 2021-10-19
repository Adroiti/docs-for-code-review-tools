Pattern: Missing use of `expose`

Issue: -

## Description

This rule enforces the component to explicitly declare the exposed properties to the component using `expose`. You can use `expose` to control the internal properties of a component so that they cannot be referenced externally.

```vue
<script>
/* ✓ GOOD */
export default {
  expose: ['increment'],
  data() {
    return { count: 0 }
  },
  methods: {
    increment() {
      this.count++
    }
  }
}
</script>


<script>
/* ✗ BAD */
export default {
  data() {
    return { count: 0 }
  },
  methods: {
    increment() {
      this.count++
    }
  }
}
</script>
```


## Further Reading

* [eslint-plugin-vue - require-expose](https://eslint.vuejs.org/rules/require-expose.html)
