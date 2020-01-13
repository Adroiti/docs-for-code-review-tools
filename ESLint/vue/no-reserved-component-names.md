Pattern: Reserved component name

Issue: -

## Description

This rule prevents name collisions between vue components and standard html elements. 

## Examples

```vue
<script>
/* ✗ BAD */
export default {
  name: 'div'
}
</script>
```

## Further Reading

* [eslint-plugin-vue - no-reserved-component-names](https://eslint.vuejs.org/rules/no-reserved-component-names.html)
