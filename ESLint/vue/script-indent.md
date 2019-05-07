Pattern: script indent

Issue: -

## Description

This rule is similar to core [indent](https://eslint.org/docs/rules/indent) rule, but it has an option for inside of `<script>` tag.

<eslint-code-block fix :rules="{'vue/script-indent': ['error']}">

```vue
<script>
let a = {
  foo: 1,
  bar: 2
}
let b = {
      foo: 1,
      bar: 2
    },
    c = {
      foo: 1,
      bar: 2
    }
const d = {
        foo: 1,
        bar: 2
      },
      e = {
        foo: 1,
        bar: 2
      }
</script>
```

</eslint-code-block>

## Options

This rule has some options.

```json
{
  "vue/script-indent": ["error", TYPE, {
    "baseIndent": 0,
    "switchCase": 0,
    "ignores": []
  }]
}
```

- `TYPE` (`number | "tab"`) ... The type of indentation. Default is `2`. If this is a number, it's the number of spaces for one indent. If this is `"tab"`, it uses one tab for one indent.
- `baseIndent` (`integer`) ... The multiplier of indentation for top-level statements. Default is `0`.
- `switchCase` (`integer`) ... The multiplier of indentation for `case`/`default` clauses. Default is `0`.
- `ignores` (`string[]`) ... The selector to ignore nodes. The AST spec is [here](https://github.com/mysticatea/vue-eslint-parser/blob/master/docs/ast.md). You can use [esquery](https://github.com/estools/esquery#readme) to select nodes. Default is an empty array.

```json
{
  "rules": {
    "vue/script-indent": ["error", 4, { "baseIndent": 1 }]
  },
  "overrides": [
    {
      "files": ["*.vue"],
      "rules": {
        "indent": "off"
      }
    }
  ]
}
```

### `2, "baseIndent": 1`
<eslint-code-block fix :rules="{'vue/script-indent': ['error', 2, { 'baseIndent': 1 }]}">

```vue
<script>
  let a = {
    foo: 1,
    bar: 2
  }
  let b = {
        foo: 1,
        bar: 2
      },
      c = {
        foo: 1,
        bar: 2
      }
  const d = {
          foo: 1,
          bar: 2
        },
        e = {
          foo: 1,
          bar: 2
        }
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - script-indent](https://eslint.vuejs.org/rules/script-indent.html)
