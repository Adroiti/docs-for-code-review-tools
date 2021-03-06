Pattern: Use of boolean default

Issue: -

## Description

The rule is to enforce the HTML standard of always defaulting boolean attributes to false.

<eslint-code-block fix :rules="{'vue/no-boolean-default': ['error']}">

```vue
<script>
export default {
  props: {
    foo: {
      type: Boolean,
      default: true
    },
    bar: {
      type: Boolean
    }
  }
}
</script>
```

</eslint-code-block>

## Options
- `'no-default'` (default) allows a prop definition object, but enforces that the `default` property not be defined.
- `'default-false'` enforces that the default can be set but must be set to `false`.

```json
  "vue/no-boolean-default": ["error", "no-default|default-false"]
```.

## Further Reading

* [eslint-plugin-vue - no-boolean-default](https://eslint.vuejs.org/rules/no-boolean-default.html)
