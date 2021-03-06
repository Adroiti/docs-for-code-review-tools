Pattern: Potential component option typo

Issue: -

## Description

This rule disallows a potential typo in your component options

**Here is the config**

```json
{
  "vue/no-potential-component-option-typo": ["error", {
    "presets": ["all"],
    "custom": ["test"]
  }]
}
```

<eslint-code-block :rules="{'vue/no-potential-component-option-typo': ['error', {presets: ['all'], custom: ['test']}]}">

```vue
<script>
export default {
  /* ✓ GOOD */
  props: {

  },
  /* ✗ BAD */
  method: {

  },
  /* ✓ GOOD */
  data: {

  },
  /* ✗ BAD */
  beforeRouteEnteR() {

  },
  /* ✗ BAD due to custom option 'test' */
  testt: {

  }
}
</script>
```

</eslint-code-block>

> we use edit distance to compare two string similarity, threshold is an option to control upper bound of edit distance to report

**Here is the another example about config option `threshold`**

```json
{
  "vue/no-potential-component-option-typo": ["error", {
    "presets": ["vue", "nuxt"],
    "threshold": 5
  }]
}
```

<eslint-code-block :rules="{'vue/no-potential-component-option-typo': ['error', {presets: ['vue', 'nuxt'], threshold: 5}]}">

```vue
<script>
export default {
  /* ✓ GOOD, due to threshold is 5 */
  props: {

  },
  /* ✗ BAD, due to threshold is 5 */
  mehtod: {

  },
  /* ✓ GOOD, due to threshold is 5 */
  data: {

  },
  /* ✓ GOOD, due to we don't choose vue-router preset or add a custom option */
  beforeRouteEnteR() {

  }
}
</script>
```

</eslint-code-block>

## Options

```json
{
  "vue/no-potential-component-option-typo": ["error", {
    "presets": ["vue"],
    "custom": [],
    "threshold": 1
  }]
}
```

- `presets` ... `enum type`, contains several common vue component option set, `["all"]` is the same as `["vue", "vue-router", "nuxt"]`. **default** `["vue"]`
- `custom` ... `array type`, a list store your custom component option want to detect. **default** `[]`
- `threshold` ... `number type`, a number used to control the upper limit of the reported editing distance, we recommend don't change this config option, even if it is required, not bigger than `2`. **default** `1`

## Further Reading

* [eslint-plugin-vue - no-potential-component-option-typo](https://eslint.vuejs.org/rules/no-potential-component-option-typo.html)
* [Edit distance](https://en.wikipedia.org/wiki/Edit_distance)
