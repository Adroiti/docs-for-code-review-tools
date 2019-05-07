Pattern: attributes order

Issue: -

## Description

This rule aims to enforce ordering of component attributes. The default order is specified in the [Vue styleguide](https://vuejs.org/v2/style-guide/#Element-attribute-order-recommended) and is:

- `DEFINITION`
  ex: 'is'
- `LIST_RENDERING`
  ex: 'v-for item in items'
- `CONDITIONALS`
  ex: 'v-if', 'v-else-if', 'v-else', 'v-show', 'v-cloak'
- `RENDER_MODIFIERS`
  ex: 'v-once', 'v-pre'
- `GLOBAL`
  ex: 'id'
- `UNIQUE`
  ex: 'ref', 'key', 'v-slot', 'slot'
- `TWO_WAY_BINDING`
  ex: 'v-model'
- `OTHER_DIRECTIVES`
  ex: 'v-custom-directive'
- `OTHER_ATTR`
  ex: 'custom-prop="foo"', 'v-bind:prop="foo"', ':prop="foo"'
- `EVENTS`
  ex: '@click="functionCall"', 'v-on="event"'
- `CONTENT`
  ex: 'v-text', 'v-html'

### the default order

<eslint-code-block fix :rules="{'vue/attributes-order': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div
    is="header"
    v-for="item in items"
    v-if="!visible"
    v-once
    id="uniqueID"
    ref="header"
    v-model="headerData"
    my-prop="prop"
    @click="functionCall"
    v-text="textContent">
  </div>
  <div
    v-for="item in items"
    v-if="!visible"
    prop-one="prop"
    :prop-two="prop"
    prop-three="prop"
    @click="functionCall"
    v-text="textContent">
  </div>
  <div
    prop-one="prop"
    :prop-two="prop"
    prop-three="prop">
  </div>

  <!-- ✗ BAD -->
  <div
    ref="header"
    v-for="item in items"
    v-once
    id="uniqueID"
    v-model="headerData"
    my-prop="prop"
    v-if="!visible"
    is="header"
    @click="functionCall"
    v-text="textContent">
  </div>
</template>
```

</eslint-code-block>

## Options
```json
{
  "vue/attributes-order": ["error", {
    "order": [
      "DEFINITION",
      "LIST_RENDERING",
      "CONDITIONALS", 
      "RENDER_MODIFIERS",
      "GLOBAL", 
      "UNIQUE", 
      "TWO_WAY_BINDING", 
      "OTHER_DIRECTIVES", 
      "OTHER_ATTR", 
      "EVENTS", 
      "CONTENT"
    ]
  }]
}
```

### Custom orders

#### `['LIST_RENDERING', 'CONDITIONALS', 'RENDER_MODIFIERS', 'GLOBAL', 'UNIQUE', 'TWO_WAY_BINDING', 'DEFINITION', 'OTHER_DIRECTIVES', 'OTHER_ATTR', 'EVENTS', 'CONTENT']`

<eslint-code-block fix :rules="{'vue/attributes-order': ['error', {order: ['LIST_RENDERING', 'CONDITIONALS', 'RENDER_MODIFIERS', 'GLOBAL', 'UNIQUE', 'TWO_WAY_BINDING', 'DEFINITION', 'OTHER_DIRECTIVES', 'OTHER_ATTR', 'EVENTS', 'CONTENT']}]}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div
    ref="header"
    is="header"
    prop-one="prop"
    prop-two="prop">
  </div>

  <!-- ✗ BAD -->
  <div
    ref="header"
    prop-one="prop"
    is="header">
  </div>
</template>
```

</eslint-code-block>

#### `[['LIST_RENDERING', 'CONDITIONALS', 'RENDER_MODIFIERS'], ['DEFINITION', 'GLOBAL', 'UNIQUE'], 'TWO_WAY_BINDING', 'OTHER_DIRECTIVES', 'OTHER_ATTR', 'EVENTS', 'CONTENT']`

<eslint-code-block fix :rules="{'vue/attributes-order': ['error', {order: [['LIST_RENDERING', 'CONDITIONALS', 'RENDER_MODIFIERS'], ['DEFINITION', 'GLOBAL', 'UNIQUE'], 'TWO_WAY_BINDING', 'OTHER_DIRECTIVES', 'OTHER_ATTR', 'EVENTS', 'CONTENT']}]}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div
    ref="header"
    is="header"
    prop-one="prop"
    prop-two="prop">
  </div>
  <div
    is="header"
    ref="header"
    prop-one="prop"
    prop-two="prop">
  </div>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - attributes-order](https://eslint.vuejs.org/rules/attributes-order.html)
