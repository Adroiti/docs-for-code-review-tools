Pattern: Malformed newline between multi-line properties

Issue: -

## Description

This rule aims at enforcing new lines between multi-line properties in Vue components to help readability

## Examples

```vue
<script>
/* ✗ BAD */
export default {
  props: {
    value: {
      type: String,
      required: true
    },
    focused: {
      type: Boolean,
      default: false,
      required: true
    },

    label: String,
    icon: String
  },
  computed: {

  }
}
</script>
```

```vue
<script>
/* ✓ GOOD */
export default {
  props: {
    value: {
      type: String,
      required: true
    },

    focused: {
      type: Boolean,
      default: false,
      required: true
    },

    label: String,
    icon: String
  },

  computed: {
    
  }
}
</script>
```

## Further Reading

* [eslint-plugin-vue - new-line-between-multi-line-property](https://eslint.vuejs.org/rules/new-line-between-multi-line-property.html)
