Pattern: Missing use of `translate()`

Issue: -

## Description

Enforces use of a translation function. Plain string literals are disallowed in JSX when enabled.

Example of **incorrect** code:

```ts
<input placeholder="Name" />
                   ~~~~~~
```

Example of **correct** code:

```ts
<input placeholder={translate('name')} />
```