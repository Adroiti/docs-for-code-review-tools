Pattern: Use of deprecated `Vue.config.keyCodes`

Issue: -

## Description

This rule reports use of deprecated `Vue.config.keyCodes` (in Vue.js 3.0.0+).

<eslint-code-block filename="a.js" language="javascript" :rules="{'vue/no-deprecated-vue-config-keycodes': ['error']}">

```js
/* ✗ BAD */
Vue.config.keyCodes = {
  // ...
}
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-deprecated-vue-config-keycodes](https://eslint.vuejs.org/rules/no-deprecated-vue-config-keycodes.html)
