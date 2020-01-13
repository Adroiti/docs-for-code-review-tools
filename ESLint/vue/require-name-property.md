Pattern: Missing `name` property

Issue: -

## Description

This rule requires a `name` property to be set on components.

## Examples

```vue
<script>
/* ✓ GOOD */
export default {
  name: 'OurButton'
}
</script>
```

```vue
<script>
/* ✗ BAD */
export default {
}
</script>
```

```vue
<script>
/* ✗ BAD */
export default {
  notName: 'OurButton'
}
</script>
```

## Further Reading

* [eslint-plugin-vue - require-name-property](https://eslint.vuejs.org/rules/require-name-property.html)
