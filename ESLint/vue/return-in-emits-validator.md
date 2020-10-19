Pattern: Missing `return` in `emits` validator

Issue: -

## Description

This rule enforces that a `return` statement is present in `emits` validators.

<eslint-code-block :rules="{'vue/return-in-emits-validator': ['error']}">

```vue
<script>
export default {
  emits: {
    /* ✓ GOOD */
    foo (evt) {
      if (evt) {
        return true
      } else {
        return false
      }
    },
    bar: function () {
      return true
    },
    baz (evt) {
      if (evt) {
        return true
      }
    },
    /* ✗ BAD */
    qux: function () {},
    quux (evt) {
      if (!evt) {
        return false
      }
    }
  }
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - return-in-emits-validator](https://eslint.vuejs.org/rules/return-in-emits-validator.html)
* [Guide - Custom Events / Validate Emitted Events](https://v3.vuejs.org/guide/component-custom-events.html#validate-emitted-events)
* [Vue RFCs - 0030-emits-option](https://github.com/vuejs/rfcs/blob/master/active-rfcs/0030-emits-option.md)
