Pattern: Malformed emotion syntax

Issue: -

## Description

This rule aims to choose between syntaxes.

Examples of **incorrect** code for this rule, when `@emotion/syntax-preference: [2, "string"]`:

```js
const H1 = styled.h1({
  color: red
})
// --> Styles should be written using strings.

const H1 = styled('h1')({
  color: red
})
// --> Styles should be written using strings.
```

Examples of **incorrect** code for this rule, when `@emotion/syntax-preference: [2, "object"]`:

```js
const H1 = styled.h1`
  color: red;
`
// --> Styles should be written using objects.

const H1 = styled('h1')`
  color: red;
`
// --> Styles should be written using objects.
```

## When Not To Use It

If you don't want to limit styles to a unique syntax.

## Further Reading

* [GitHub - syntax-preference](https://github.com/emotion-js/emotion/blob/main/packages/eslint-plugin/docs/rules/syntax-preference.md)