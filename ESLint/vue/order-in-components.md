Pattern: Wrong property order in component

Issue: -

## Description

This rule makes sure you keep declared order of properties in components. Recommended order of properties can be [found here](https://vuejs.org/v2/style-guide/#Component-instance-options-order-recommended).

<eslint-code-block fix :rules="{'vue/order-in-components': ['error']}">

```vue
<script>
/* ✓ GOOD */
export default {
  name: 'app',
  props: {
    propA: Number
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>
```

</eslint-code-block>

<eslint-code-block fix :rules="{'vue/order-in-components': ['error']}">

```vue
<script>
/* ✗ BAD */
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  props: {
    propA: Number
  }
}
</script>
```

</eslint-code-block>

## Options

```json
{
  "vue/order-in-components": ["error", {
    "order": [
      "el",
      "name",
      "parent",
      "functional",
      ["delimiters", "comments"],
      ["components", "directives", "filters"],
      "extends",
      "mixins",
      "inheritAttrs",
      "model",
      ["props", "propsData"],
      "data",
      "computed",
      "watch",
      "LIFECYCLE_HOOKS",
      "methods",
      ["template", "render"],
      "renderError"
    ]
  }]
}
```

- `order` (`(string | string[])[]`) ... The order of properties. Elements are the property names or `LIFECYCLE_HOOKS`. If an element is the array of strings, it means any of those can be placed there unordered. Default is above.

## Further Reading

* [eslint-plugin-vue - order-in-components](https://eslint.vuejs.org/rules/order-in-components.html)
