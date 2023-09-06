Pattern: Use of old color class structure

Issue: -

## Description

This rule disallows the use of the old color class structure.

Examples of **incorrect** code for this rule:

```html
<v-btn color="primary darken-1">
<div class="primary"></div>
<div class="primary--text"></div>
<div class="primary--text text--darken-1"></div>
```

Examples of **correct** code for this rule:

```js
<v-btn color="primary">
<v-btn color="primary-darken-1">
<div class="bg-primary"></div>
<div class="text-primary"></div>
<div class="text-primary-darken-1"></div>
```

## Further Reading

* [eslint-plugin-vuetify - no-deprecated-colors](https://github.com/vuetifyjs/eslint-plugin-vuetify/blob/HEAD/docs/rules/no-deprecated-events.md)
