Pattern: Too many property values in declaration

Issue: -

## Description

Limit the number of values for a list of properties within declarations.

## Examples

If a property name is surrounded with `"/"` (e.g. `"/^margin/"`), it is interpreted as a regular expression. This allows, for example, easy targeting of shorthands: `/^margin/` will match `margin`, `margin-top`, `margin-inline`, etc.

Given:

```json
{
  "border": 2,
  "/^margin/": 1,
},
```

The following patterns are considered violations:

```css
a { border: 1px solid blue; }
```

```css
a { margin: 1px 2px; }
```

```css
a { margin-inline: 1px 2px; }
```

The following patterns are *not* considered violations:

```css
a { border: 1px solid; }
```

```css
a { margin: 1px; }
```

```css
a { margin-inline: 1px; }
```

## Further Reading

* [stylelint - declaration-property-max-values](https://stylelint.io/user-guide/rules/list/declaration-property-max-values)