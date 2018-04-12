Pattern: Malformed property value

Issue: -

## Description

This rules enforces either variables (`$sass`, `@less`, `var(--cssnext)`), functions or custom CSS keywords (`inherit`, `none`, etc.) for property's values.

Example of **incorrect** code:

```css
a { color: #FFF; }

a { color: inherit; }

a { color: currentColor; }
```

Example of **correct** code:

```css
a { color: var(--color-white); }

a { color: -var(--color-white); }

a { color: color(red alpha(-10%)); }
```

## Default configuration

```js
// defaults
{
  ignoreVariables: true,
  ignoreFunctions: true,
  ignoreKeywords: null,
}
```

## Further Reading

* [GitHub - stylelint-declaration-strict-value](https://github.com/AndyOGo/stylelint-declaration-strict-value#primary-options)