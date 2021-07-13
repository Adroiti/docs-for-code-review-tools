Pattern: ES module exports in `<script setup>`

Issue: -

## Description

This rule warns ES module exports in `<script setup>`.

The previous version of `<script setup>` RFC used `export` to define variables used in templates, but the new `<script setup>` RFC has been updated to define without using `export`.

<eslint-code-block :rules="{'vue/no-export-in-script-setup': ['error']}">

```vue
<script setup>
/* ✓ GOOD */
let msg = 'Hello!'
</script>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/no-export-in-script-setup': ['error']}">

```vue
<script setup>
/* ✗ BAD */
export let msg = 'Hello!'
</script>
```

</eslint-code-block>


## Further Reading

* [eslint-plugin-vue - no-export-in-script-setup](https://eslint.vuejs.org/rules/no-export-in-script-setup.html)
