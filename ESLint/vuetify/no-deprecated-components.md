Pattern: Use of deprecated component

Issue: -

## Description

Disallows the use of removed and deprecated components. Grid components are not included in this rule, use `no-legacy-grid` instead.

Example of **incorrect** code:

```html
<v-content>
  <v-list-tile>
    <v-list-tile-title></v-list-tile-title>
  </v-list-tile>
</v-content>

<v-jumbotron></v-jumbotron>
```

Example of **correct** code:

```html
<v-main>
  <v-list-item>
    <v-list-item-title></v-list-item-title>
  </v-list-item>
</v-main>
```

## Further Reading

* [eslint-plugin-vuetify - no-deprecated-components](https://github.com/vuetifyjs/eslint-plugin-vuetify/blob/master/docs/rules/no-deprecated-components.md)
