Pattern: Malformed use of `lang`

Issue: -

## Description

Disallows the use of languages other than those available in the your application for the lang attribute of block elements.

## Examples

```vue
<!-- ✓ GOOD -->
<script lang="ts">
</script>


<!-- ✗ BAD -->
<script>
</script>
```

## Further Reading

* [eslint-plugin-vue - block-lang](https://eslint.vuejs.org/rules/block-lang.html)
