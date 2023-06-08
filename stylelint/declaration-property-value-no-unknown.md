Pattern: Unknown value for property within declaration

Issue: -

## Description

Disallows unknown values for properties within declarations.

This rule considers values for properties defined within the CSS specifications to be known. You can use the `propertiesSyntax` and `typesSyntax` secondary options to extend the syntax.

This rule is only appropriate for CSS. You should not turn it on for CSS-like languages, such as Sass or Less, as they have their own syntaxes.

## Examples

The following patterns are considered violations:

```css
a { top: red; }
```

```css
a { top: unknown; }
```

The following patterns are *not* considered violations:

```css
a { top: 0; }
```

```css
a { top: var(--foo); }
```

## Further Reading

* [stylelint - declaration-property-value-no-unknown](https://stylelint.io/user-guide/rules/declaration-property-value-no-unknown)