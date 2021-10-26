Pattern: Missing `var` for custom property

Issue: -

## Description

Disallow missing `var` function for custom properties.

```css
    :root { --foo: red; }
    a { color: --foo; }
/**            ↑
 *             This custom property */
```

This rule only reports custom properties that are defined within the same source.

## Examples

### `true`

The following patterns are considered problems:

<!-- prettier-ignore -->
```css
:root { --foo: red; }
a { color: --foo; }
```

<!-- prettier-ignore -->
```css
@property --foo {}
a { color: --foo; }
```

The following patterns are _not_ considered problems:

<!-- prettier-ignore -->
```css
:root { --foo: red; }
a { color: var(--foo); }
```

<!-- prettier-ignore -->
```css
@property --foo {}
a { color: var(--foo); }
```

## Further Reading

* [stylelint - custom-property-no-missing-var-function](https://stylelint.io/user-guide/rules/custom-property-no-missing-var-function)