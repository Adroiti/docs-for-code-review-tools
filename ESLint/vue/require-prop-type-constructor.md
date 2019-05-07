Pattern: require prop type constructor

Issue: -

## Description

This rule reports prop types that can't be presumed as constructors.

It's impossible to catch every possible case and know whether the prop type is a constructor or not, hence this rule black list few types of nodes, instead of white-listing correct ones.

The following types are forbidden and will be reported:

- Literal
- TemplateLiteral
- BinaryExpression
- UpdateExpression

It will catch most commonly made mistakes which are using strings instead of constructors.

<eslint-code-block fix :rules="{'vue/require-prop-type-constructor': ['error']}">

```vue
<script>
export default {
  props: {
    /* ✓ GOOD */
    myProp: Number,
    anotherProp: [Number, String],
    myFieldWithBadType: {
      type: Object,
      default: function() {
        return {}
      },
    },
    myOtherFieldWithBadType: {
      type: Number,
      default: 1,
    },
    /* ✗ BAD */
    myProp: "Number",
    anotherProp: ["Number", "String"],
    myFieldWithBadType: {
      type: "Object",
      default: function() {
        return {}
      },
    },
    myOtherFieldWithBadType: {
      type: "Number",
      default: 1,
    },
  }
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - require-prop-type-constructor](https://eslint.vuejs.org/rules/require-prop-type-constructor.html)
