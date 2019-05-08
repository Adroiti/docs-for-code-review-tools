Pattern: Mismatched component file name

Issue: -

## Description

This rule reports if a component name property does not match its file name.

You can define an array of file extensions this rule should verify for the component's name.

```json
{
  "vue/match-component-file-name": ["error", {
    "extensions": ["jsx"],
    "shouldMatchCase": false
  }]
}
```

By default this rule will only verify components in a file with a `.jsx` extension.

You can use any combination of `".jsx"`, `".vue"` and `".js"` extensions.

You can also enforce same case between the component's name and its file name.

If you are defining multiple components within the same file, this rule will be ignored.

<eslint-code-block filename="src/MyComponent.jsx" language="javascript" :rules="{'vue/match-component-file-name': ['error']}">

```jsx
// file name: src/MyComponent.jsx
export default {
  /* ✓ GOOD */
  name: 'MyComponent',
  render() {
    return <h1>Hello world</h1>
  }
}
```

</eslint-code-block>

<eslint-code-block filename="src/MyComponent.jsx" language="javascript" :rules="{'vue/match-component-file-name': ['error']}">

```jsx
// file name: src/MyComponent.jsx
export default {
  /* ✓ GOOD */
  name: 'my-component',
  render() { return <div /> }
}
```

</eslint-code-block>

<eslint-code-block filename="src/MyComponent.jsx" language="javascript" :rules="{'vue/match-component-file-name': ['error']}">

```jsx
// file name: src/MyComponent.jsx
export default {
  /* ✗ BAD */
  name: 'MComponent', // note the missing y
  render() {
    return <h1>Hello world</h1>
  }
}
```

</eslint-code-block>

<eslint-code-block filename="src/MyComponent.jsx" language="javascript" :rules="{'vue/match-component-file-name': ['error']}">

```jsx
// file name: src/MyComponent.jsx
/* no name property defined */
export default {
  render() {
    return <h1>Hello world</h1>
  }
}
```

</eslint-code-block>

<eslint-code-block filename="src/MyComponent.vue" :rules="{'vue/match-component-file-name': ['error']}">

```vue
<!-- file name: src/MyComponent.vue -->
<script>
  export default {
    /* The default does not verify to `.vue`. */
    name: 'MComponent',
    template: '<div />'
  }
</script>
```

</eslint-code-block>

## Options

```json
{
  "vue/match-component-file-name": ["error", {
    "extensions": ["jsx"],
    "shouldMatchCase": false
  }]
}
```

- `"extensions": []` ... array of file extensions to be verified. Default is set to `["jsx"]`.
- `"shouldMatchCase": false` ... boolean indicating if component's name
  should also match its file name case. Default is set to `false`.

### `{extensions: ["vue"]}`

<eslint-code-block filename="src/MyComponent.vue" :rules="{'vue/match-component-file-name': ['error', {extensions: ['vue']}]}">

```vue
<!-- file name: src/MyComponent.vue -->
<script>
  export default {
    /* ✓ GOOD */
    name: 'MyComponent',
    template: '<div />'
  }
</script>
```

</eslint-code-block>

<eslint-code-block filename="src/MyComponent.vue" :rules="{'vue/match-component-file-name': ['error', {extensions: ['vue']}]}">

```vue
<!-- file name: src/MyComponent.vue -->
<script>
  export default {
    /* ✗ BAD */
    name: 'MComponent',
    template: '<div />'
  }
</script>
```

</eslint-code-block>

<eslint-code-block filename="src/MyComponent.vue" :rules="{'vue/match-component-file-name': ['error', {extensions: ['vue']}]}">

```vue
<!-- file name: src/MyComponent.vue -->
<script>
  /* no name property defined */
  export default {
    template: '<div />'
  }
</script>
```

</eslint-code-block>

### `{extensions: ["js"]}`

<eslint-code-block filename="src/MyComponent.js" language="javascript" :rules="{'vue/match-component-file-name': ['error', {extensions: ['js']}]}">

```js
// file name: src/MyComponent.js
new Vue({
  /* ✓ GOOD */
  name: 'MyComponent',
  template: '<div />'
})
```

</eslint-code-block>

<eslint-code-block filename="src/MyComponent.js" language="javascript" :rules="{'vue/match-component-file-name': ['error', {extensions: ['js']}]}">

```js
// file name: src/MyComponent.js
/* ✓ GOOD */
Vue.component('MyComponent', {
  template: '<div />'
})
```

</eslint-code-block>

<eslint-code-block filename="src/MyComponent.js" language="javascript" :rules="{'vue/match-component-file-name': ['error', {extensions: ['js']}]}">

```js
// file name: src/MyComponent.js
new Vue({
  /* ✗ BAD */
  name: 'MComponent',
  template: '<div />'
})
```

</eslint-code-block>

<eslint-code-block filename="src/MyComponent.js" language="javascript" :rules="{'vue/match-component-file-name': ['error', {extensions: ['js']}]}">

```js
// file name: src/MyComponent.js
/* ✗ BAD */
Vue.component('MComponent', {
  template: '<div />'
})
```

</eslint-code-block>

<eslint-code-block filename="src/components.js" language="javascript" :rules="{'vue/match-component-file-name': ['error', {extensions: ['js']}]}">

```js
// file name: src/components.js
/* defines multiple components, so this rule is ignored */
Vue.component('MyComponent', {
  template: '<div />'
})

Vue.component('OtherComponent', {
  template: '<div />'
})

new Vue({
  name: 'ThirdComponent',
  template: '<div />'
})
```

</eslint-code-block>

<eslint-code-block filename="src/MyComponent.js" language="javascript" :rules="{'vue/match-component-file-name': ['error', {extensions: ['js']}]}">

```js
// file name: src/MyComponent.js
/* no name property defined */
new Vue({
  template: '<div />'
})
```

</eslint-code-block>

### `{shouldMatchCase: true}`

<eslint-code-block filename="src/MyComponent.jsx" language="javascript" :rules="{'vue/match-component-file-name': ['error',  {shouldMatchCase: true}]}">

```jsx
// file name: src/MyComponent.jsx
export default {
  /* ✓ GOOD */
  name: 'MyComponent',
  render() { return <div /> }
}
```

</eslint-code-block>

<eslint-code-block filename="src/my-component.jsx" language="javascript" :rules="{'vue/match-component-file-name': ['error',  {shouldMatchCase: true}]}">

```jsx
// file name: src/my-component.jsx
export default {
  /* ✓ GOOD */
  name: 'my-component',
  render() { return <div /> }
}
```

</eslint-code-block>

<eslint-code-block filename="src/MyComponent.jsx" language="javascript" :rules="{'vue/match-component-file-name': ['error', {shouldMatchCase: true}]}">

```jsx
// file name: src/MyComponent.jsx
export default {
  /* ✗ BAD */
  name: 'my-component',
  render() { return <div /> }
}
```

</eslint-code-block>

<eslint-code-block filename="src/my-component.jsx" language="javascript" :rules="{'vue/match-component-file-name': ['error', {shouldMatchCase: true}]}">

```jsx
// file name: src/my-component.jsx
export default {
  /* ✗ BAD */
  name: 'MyComponent',
  render() { return <div /> }
}
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - match-component-file-name](https://eslint.vuejs.org/rules/match-component-file-name.html)
