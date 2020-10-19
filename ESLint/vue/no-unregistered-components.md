Pattern: Use of unregistered component

Issue: -

## Description

This rule reports components that haven't been registered and are being used in the template.

<eslint-code-block :rules="{'vue/no-unregistered-components': ['error']}">

```vue
<!-- ✓ GOOD -->
<template>
  <div>
    <h2>Lorem ipsum</h2>
    <the-modal>
      <component is="TheInput" />
      <component :is="'TheDropdown'" />
      <TheButton>CTA</TheButton>
    </the-modal>
  </div>
</template>

<script>
  import TheButton from 'components/TheButton.vue'
  import TheModal from 'components/TheModal.vue'
  import TheInput from 'components/TheInput.vue'
  import TheDropdown from 'components/TheDropdown.vue'

  export default {
    components: {
      TheButton,
      TheModal,
      TheInput,
      TheDropdown,
    }
  }
</script>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/no-unregistered-components': ['error']}">

```vue
<!-- ✗ BAD -->
<template>
  <div>
    <h2>Lorem ipsum</h2>
    <TheModal />
  </div>
</template>

<script>
  export default {
    components: {

    }
  }
</script>
```

</eslint-code-block>

## Options

```json
{
  "vue/no-unregistered-components": ["error", {
    "ignorePatterns": []
  }]
}
```

- `ignorePatterns` Suppresses all errors if component name matches one or more patterns.

### `ignorePatterns: ['custom(\\-\\w+)+']`

<eslint-code-block :rules="{'vue/no-unregistered-components': ['error', { 'ignorePatterns': ['custom(\\-\\w+)+'] }]}">

```vue
<!-- ✓ GOOD -->
<template>
  <div>
    <h2>Lorem ipsum</h2>
    <CustomComponent />
  </div>
</template>

<script>
  export default {
    components: {

    },
  }
</script>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/no-unregistered-components': ['error', { 'ignorePatterns': ['custom(\\-\\w+)+'] }]}">

```vue
<!-- ✗ BAD -->
<template>
  <div>
    <h2>Lorem ipsum</h2>
    <WarmButton />
  </div>
</template>

<script>
  export default {
    components: {

    },
  }
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-unregistered-components](https://eslint.vuejs.org/rules/no-unregistered-components.html)
