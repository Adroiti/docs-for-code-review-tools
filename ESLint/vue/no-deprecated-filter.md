Pattern: Use of deprecated `filters` syntax

Issue: -

## Description

This rule reports deprecated `filters` syntax (removed in Vue.js v3.0.0+).

<eslint-code-block :rules="{'vue/no-deprecated-filter': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  {{ filter(msg) }}
  {{ filter(msg, '€') }}
  {{ filterB(filterA(msg)) }}
  <div v-bind:id="filter(msg)"></div>
  <div v-bind:id="filter(msg, '€')"></div>
  <div v-bind:id="filterB(filterA(msg))"></div>

  <!-- ✗ BAD -->
  {{ msg | filter }}
  {{ msg | filter('€') }}
  {{ msg | filterA | filterB }}
  <div v-bind:id="msg | filter"></div>
  <div v-bind:id="msg | filter('€')"></div>
  <div v-bind:id="msg | filterA | filterB"></div>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-deprecated-filter](https://eslint.vuejs.org/rules/no-deprecated-filter.html)
* [Migration Guide - Filters](https://v3.vuejs.org/guide/migration/filters.html)
* [Vue RFCs - 0015-remove-filters](https://github.com/vuejs/rfcs/blob/master/active-rfcs/0015-remove-filters.md)