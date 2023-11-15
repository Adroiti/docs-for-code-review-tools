Pattern: Use of removed slot variable

Issue: -

## Description

Prevents the use of removed slot variables.

Examples of **incorrect** code for this rule:

```html
<v-dialog>
  <template #activator="{ on }">
    <v-btn v-on="on" />
  </template>
</v-dialog>
```

Examples of **correct** code for this rule:

```html
<v-dialog>
  <template #activator="{ props }">
    <v-btn v-bind="props" />
  </template>
</v-dialog>
```

## Further Reading

* [eslint-plugin-vuetify - no-deprecated-slots](https://github.com/vuetifyjs/eslint-plugin-vuetify/blob/HEAD/docs/rules/no-deprecated-slots.md)
