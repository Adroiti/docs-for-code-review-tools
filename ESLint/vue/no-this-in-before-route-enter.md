Pattern: Use of `this` in `beforeRouteEnter`

Issue: -

## Description

Because lack of `this` in the `beforeRouteEnter` [(docs)](https://router.vuejs.org/guide/advanced/navigation-guards.html#in-component-guards). This behavior isn't obvious, so it's pretty easy to make a `TypeError`.

<eslint-code-block :rules="{'vue/no-this-in-before-route-enter': ['error']}">

```vue
<script>
export default {
  beforeRouteEnter() {
    /* ✗ BAD */
    this.method(); // Uncaught TypeError: Cannot read property 'method' of undefined
    this.attribute = 42;
    if (this.value === 42) {
    }
    this.attribute = this.method();
  }   
}
</script>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/no-this-in-before-route-enter': ['error']}">

```vue
<script>
export default {
  beforeRouteEnter() {
    /* ✓ GOOD */
    // anything without this
  }   
}
</script>
```

</eslint-code-block>


## Further Reading

* [eslint-plugin-vue - no-this-in-before-route-enter](https://eslint.vuejs.org/rules/no-this-in-before-route-enter.html)
