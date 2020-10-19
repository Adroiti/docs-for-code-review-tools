Pattern: Passing multiple arguments to scoped slots

Issue: -

## Description

This rule disallows to pass multiple arguments to scoped slots.  
In details, it reports call expressions if a call of `this.$scopedSlots` members has 2 or more arguments.

<eslint-code-block :rules="{'vue/no-multiple-slot-args': ['error']}">

```vue
<script>
export default {
  render(h) {
    /* ✓ GOOD */
    var children = this.$scopedSlots.default()
    var children = this.$scopedSlots.default(foo)
    var children = this.$scopedSlots.default({ foo, bar })

    /* ✗ BAD */
    var children = this.$scopedSlots.default(foo, bar)
    var children = this.$scopedSlots.default(...foo)
  }
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-multiple-slot-args](https://eslint.vuejs.org/rules/no-multiple-slot-args.html)
