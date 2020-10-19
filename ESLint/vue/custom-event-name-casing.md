Pattern: Inconsisten custom event name casing

Issue: -

## Description

This rule enforces using kebab-case custom event names.

> Event names will never be used as variable or property names in JavaScript, so there’s no reason to use camelCase or PascalCase. Additionally, `v-on` event listeners inside DOM templates will be automatically transformed to lowercase (due to HTML’s case-insensitivity), so `v-on:myEvent` would become `v-on:myevent` – making `myEvent` impossible to listen to.
>
> For these reasons, we recommend you **always use kebab-case for event names**.


<eslint-code-block :rules="{'vue/custom-event-name-casing': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <button @click="$emit('my-event')" />

  <!-- ✗ BAD -->
  <button @click="$emit('myEvent')" />
</template>
<script>
export default {
  methods: {
    onClick () {
      /* ✓ GOOD */
      this.$emit('my-event')
      this.$emit('update:myProp', myProp)

      /* ✗ BAD */
      this.$emit('myEvent')
    }
  }
}
</script>
```

</eslint-code-block>

## Options

```json
{
  "vue/custom-event-name-casing": ["error", {
    "ignores": []
  }]
}
```

- `ignores` (`string[]`) ... The event names to ignore. Sets the event name to allow. For example, custom event names, Vue components event with special name, or Vue library component event name. You can set the regexp by writing it like `"/^name/"` or `click:row` or `fooBar`.

### `"ignores": ["fooBar", "/^[a-z]+(?:-[a-z]+)*:[a-z]+(?:-[a-z]+)*$/u"]`

<eslint-code-block :rules="{'vue/custom-event-name-casing': ['error', { ignores: ['fooBar', '/^[a-z]+(?:-[a-z]+)*:[a-z]+(?:-[a-z]+)*$/u'] }]}">

```vue
<template>
  <!-- ✓ GOOD -->
  <button @click="$emit('click:row')" />
  <button @click="$emit('fooBar')" />

  <!-- ✗ BAD -->
  <button @click="$emit('myEvent')" />
</template>
<script>
export default {
  methods: {
    onClick () {
      /* ✓ GOOD */
      this.$emit('click:row')
      this.$emit('fooBar')

      /* ✗ BAD */
      this.$emit('myEvent')
    }
  }
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - custom-event-name-casing](https://eslint.vuejs.org/rules/custom-event-name-casing.html)
