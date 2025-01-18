Pattern: Redundant boolean literal comparison

Issue: -

## Description

Comparing boolean values to boolean literals is redundant and makes code less readable. Using the boolean value directly, or via a unary negation (`!value`), is more concise and clearer. A comparison is considered unnecessary if it checks a boolean literal against any variable with just the `boolean` type, but not if the type is a union including booleans.

## Examples

Example of **incorrect** code:
```ts
declare const someCondition: boolean;
if (someCondition === true) {
}
```

Example of **correct** code:
```ts
declare const someCondition: boolean;
if (someCondition) {
}

declare const someObjectBoolean: boolean | Record<string, unknown>;
if (someObjectBoolean === true) {
}

declare const someStringBoolean: boolean | string;
if (someStringBoolean === true) {
}
```