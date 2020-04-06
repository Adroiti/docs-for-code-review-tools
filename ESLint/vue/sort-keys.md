Pattern: Wrong object key order

Issue: -

## Description

Checks all property definitions of object expressions and verifies that all variables are sorted alphabetically.

## Options


```json
{
    "sort-keys": ["error", "asc", {
        "caseSensitive": true,
        "ignoreChildrenOf": ["model"],
        "ignoreGrandchildrenOf": ["computed", "directives", "inject", "props", "watch"],
        "minKeys": 2,
        "natural": false
  }]
}
```

The 1st option is `"asc"` or `"desc"`.

* `"asc"` (default) - enforce properties to be in ascending order.
* `"desc"` - enforce properties to be in descending order.

The 2nd option is an object which has 5 properties.

* `caseSensitive` - if `true`, enforce properties to be in case-sensitive order. Default is `true`.
* `ignoreChildrenOf` - an array of properties to ignore the children of.  Default is `["model"]`
* `ignoreGrandchildrenOf` - an array of properties to ignore the grandchildren sort order. Default is `["computed", "directives", "inject", "props", "watch"]`
* `minKeys` - Specifies the minimum number of keys that an object should have in order for the object's unsorted keys to produce an error. Default is `2`, which means by default all objects with unsorted keys will result in lint errors.
* `natural` - if `true`, enforce properties to be in natural order. Default is `false`. Natural Order compares strings containing combination of letters and numbers in the way a human being would sort. It basically sorts numerically, instead of sorting alphabetically. So the number 10 comes after the number 3 in Natural Sorting.

While using this rule, you may disable the normal `sort-keys` rule.  This rule will apply to plain js files as well as Vue component scripts.

## :book: Rule Details

This rule forces many dictionary properties to be in alphabetical order while allowing `order-in-components`, property details,
and other similar fields not to be in alphabetical order.

<eslint-code-block fix :rules="{'vue/sort-keys': ['error']}">

```vue
<script>
/* ✓ GOOD */
export default {
  name: 'app',
  model: {
    prop: 'checked',
    event: 'change'
  },
  props: {
    propA: {
      type: String,
      default: 'abc',
    },
    propB: {
      type: String,
      default: 'abc',
    },
  },
}
</script>
```

</eslint-code-block>

<eslint-code-block fix :rules="{'vue/sort-keys': ['error']}">

```vue
<script>
/* ✗ BAD */
export default {
  name: 'app',
  model: {
    prop: 'checked',
    event: 'change'
  },
  props: {
    propB: {
      type: String,
      default: 'abc',
    },
    propA: {
      type: String,
      default: 'abc',
    },
  },
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - sort-keys](https://eslint.vuejs.org/rules/sort-keys.html)
