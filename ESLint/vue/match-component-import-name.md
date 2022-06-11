Pattern: Unmatched component import name

Issue: -

## Description

By default, this rule will validate that the imported name matches the name of the components object property identifier. Note that "matches" means that the imported name matches either the PascalCase or kebab-case version of the components object property identifier. If you would like to enforce that it must match only one of PascalCase or kebab-case, use this rule in conjunction with the rule [vue/component-definition-name-casing](./component-definition-name-casing.md).

<eslint-code-block :rules="{'vue/match-component-import-name': ['error']}">

```vue
<script>
export default {
  components: {
    /* ✓ GOOD */
    AppButton,
    AppButton: AppButton,
    'app-button': AppButton,

    /* ✗ BAD */
    SomeOtherName: AppButton,
    'some-other-name': AppButton
  }
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - match-component-import-name](https://eslint.vuejs.org/rules/match-component-import-name.html)
