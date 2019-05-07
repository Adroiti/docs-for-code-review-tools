Pattern: return in computed property

Issue: -

## Description

This rule enforces that a `return` statement is present in `computed` properties.

<eslint-code-block :rules="{'vue/return-in-computed-property': ['error']}">

```vue
<script>
export default {
  computed: {
    /* ✓ GOOD */
    foo () {
      if (this.bar) {
        return this.baz
      } else {
        return this.baf
      }
    },
    bar: function () {
      return false
    },
    /* ✗ BAD */
    baz () {
      if (this.baf) {
        return this.baf
      }
    },
    baf: function () {}
  }
}
</script>
```

</eslint-code-block>

## Options

```json
{
  "vue/return-in-computed-property": ["error", {
    "treatUndefinedAsUnspecified": true
  }]
}
```

This rule has an object option:
- `"treatUndefinedAsUnspecified"`: `true` (default) disallows implicitly returning undefined with a `return` statement.

### `treatUndefinedAsUnspecified: false`

<eslint-code-block :rules="{'vue/return-in-computed-property': ['error', { treatUndefinedAsUnspecified: false }]}">

```vue
<script>
export default {
  computed: {
    /* ✓ GOOD */
    foo () {
      if (this.bar) {
        return undefined
      } else {
        return
      }
    },
    bar: function () {
      return
    },
    /* ✗ BAD */
    baz () {
      if (this.baf) {
        return this.baf
      }
    },
    baf: function () {}
  }
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - return-in-computed-property](https://eslint.vuejs.org/rules/return-in-computed-property.html)
