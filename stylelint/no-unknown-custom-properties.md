Pattern: Unknown custom property

Issue: -

## Description

Disallows unknown custom properties.

<!-- prettier-ignore -->
```css
a { color: var(--foo); }
/**            ↑
 *             This custom property */

a { color: var(--foo, var(--bar)); }
/**                       ↑
 *                        And this one */
```

This rule considers custom properties defined within the same source to be known.

## Examples

The following patterns are considered problems:

<!-- prettier-ignore -->
```css
a { color: var(--foo); }
```

<!-- prettier-ignore -->
```css
a { color: var(--foo, var(--bar)); }
```

The following patterns are _not_ considered problems:

<!-- prettier-ignore -->
```css
a { --foo: #f00; color: var(--foo); }
```

<!-- prettier-ignore -->
```css
a { color: var(--foo, #f00); }
```

<!-- prettier-ignore -->
```css
a { --foo: #f00; color: var(--bar, var(--foo)); }
```

<!-- prettier-ignore -->
``` css
@property --foo { syntax: "<color>"; inherits: false; initial-value: #f00; }
a { color: var(--foo); }
```

## Further Reading

* [stylelint - no-unknown-custom-properties](https://stylelint.io/user-guide/rules/no-unknown-custom-properties/)