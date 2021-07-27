Pattern: Use of deprecated prop

Issue: -

## Description

Disallows the use of removed and deprecated props.

Examples of **incorrect** code for this rule:

```html
<v-btn outline round />
<v-carousel hide-controls />
<v-toolbar app manual-scroll />
```

Examples of **correct** code for this rule:

```html
<v-btn outlined rounded />
<v-carousel :show-arrows="false" />
<v-app-bar app :value="false" />
```

## Further Reading

* [eslint-plugin-vuetify - no-deprecated-classes](https://github.com/vuetifyjs/eslint-plugin-vuetify/blob/master/docs/rules/no-deprecated-props.md)
