Pattern: Use of deprecated event

Issue: -

## Description

This rule disallows the use of removed and deprecated events. 

Examples of **incorrect** code for this rule:

```html
<v-text-field @input="onInput" />
<v-btn @change="onSelected" />
```

Examples of **correct** code for this rule:

```html
<v-text-field @update:model-value="onInput" />
<v-btn @group:selected="onSelected" />
```

## Further Reading

* [eslint-plugin-vuetify - no-deprecated-events](https://github.com/vuetifyjs/eslint-plugin-vuetify/blob/HEAD/docs/rules/no-deprecated-events.md)
