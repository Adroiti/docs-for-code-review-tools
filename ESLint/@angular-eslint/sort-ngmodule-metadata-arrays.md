Pattern: Wrong order for NgModule metadata array

Issue: -

## Description

This rule enforces that NgModule metadata arrays have a sorted list of identifiers. Objects such as provider definitions, call expressions and computed members will be ignored for sorting purposes. Sorting is based on simple string localeCompare.

## Rule Details

Examples of **incorrect** code for this rule:

```ts
@NgModule({
  providers: [_Provider, BProvider, AProvider, CProvider],
})
export class AppModule {}
```

Example of **correct** code for this rule:

```ts
@Component({
  providers: [_Provider, AProvider, BProvider, CProvider],
})
export class AppComponent {}
```

## Further Reading

* [GitHub - sort-ngmodule-metadata-arrays](https://github.com/angular-eslint/angular-eslint/blob/master/packages/eslint-plugin/docs/rules/sort-ngmodule-metadata-arrays.md)