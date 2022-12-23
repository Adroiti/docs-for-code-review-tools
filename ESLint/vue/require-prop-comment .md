Pattern: Missing comment for prop

Issue: -

## Description

This rule enforces that every prop has a comment that documents it.

```vue
<script>
export default defineComponent({
  props: {
    // ✓ GOOD

    /** JSDoc comment */
    a: Number,

    // ✗ BAD

    // line comment
    b: Number,

    /* block comment */
    c: Number,

    d: Number,
  }
})
</script>
```

## Further Reading

* [eslint-plugin-vue - require-prop-comment ](https://eslint.vuejs.org/rules/require-prop-comment.html)
