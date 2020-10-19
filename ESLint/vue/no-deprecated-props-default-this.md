Pattern: Use of `this` within the props default value factory function

Issue: -

## Description

This rule reports the use of `this` within the props default value factory functions. In Vue.js 3.0.0+, props default value factory functions no longer have access to `this`.

<eslint-code-block :rules="{'vue/no-deprecated-props-default-this': ['error']}">

```vue
<script>
export default {
  props: {
    a: String,
    b: {
      default () {
        /* ✗ BAD */
        return this.a
      }
    }
  }
}
</script>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/no-deprecated-props-default-this': ['error']}">

```vue
<script>
export default {
  props: {
    a: String,
    b: {
      default (props) {
        /* ✓ GOOD */
        return props.a
      }
    }
  }
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-deprecated-props-default-this](https://eslint.vuejs.org/rules/no-deprecated-props-default-this.html)
* [Migration Guide - Props Default Function `this` Access](https://v3.vuejs.org/guide/migration/props-default-this.html)