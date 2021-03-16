Pattern: Invalid named grid area

Issue: -

## Description

Detects invalid named grid areas.

<!-- prettier-ignore -->
```css
a { grid-template-areas:
      "a a a"
      "b b b"; }
/**   ↑
 *  This named grid area */
```

For a named grid area to be valid, all strings must define:

- the same number of cell tokens
- at least one cell token

And all named grid areas that spans multiple grid cells must form a single filled-in rectangle.

## Examples

The following patterns are considered violations:

<!-- prettier-ignore -->
```css
a { grid-template-areas: "" }
```

<!-- prettier-ignore -->
```css
a { grid-template-areas: "a a a"
                         "b b b b"; }
```

<!-- prettier-ignore -->
```css
a { grid-template-areas: "a a a"
                         "b b a"; }
```

The following pattern is _not_ considered a violation:

<!-- prettier-ignore -->
```css
a { grid-template-areas: "a a a"
                         "b b b"; }
```

## Further Reading

* [stylelint - named-grid-areas-no-invalid](https://stylelint.io/user-guide/rules/named-grid-areas-no-invalid)