Pattern: Duplicate font family name

Issue: -

## Description

This rule checks the `font` and `font-family` properties.

This rule ignores `$sass`, `@less`, and `var(--custom-property)` variable syntaxes.

**Caveat:** This rule will stumble on *unquoted* multi-word font names and *unquoted* font names containing escape sequences. Wrap these font names in quotation marks, and everything should be fine.

## Examples

The following patterns are considered violations:

```css
a { font-family: serif, serif; }
/**              ↑      ↑
 * These font family names */
```

```css
a { font-family: 'Times', Times, serif; }
```

```css
a { font: 1em "Arial", 'Arial', sans-serif; }
```

```css
a { font: normal 14px/32px -apple-system, BlinkMacSystemFont, sans-serif, sans-serif; }
```

The following patterns are *not* considered violations:

```css
a { font-family: Times, serif; }
```

```css
a { font: 1em "Arial", "sans-serif", sans-serif; }
```

```css
a { font: normal 14px/32px -apple-system, BlinkMacSystemFont, sans-serif; }
```

# Configuration

### `ignoreFontFamilyNames: ["/regex/", "string"]`

Given:

```js
["/^Some Font /", "monospace"]
```

The following patterns are *not* considered violations:

```css
font-family: monospace, monospace
```

```css
font-family: "Some Font Family", "Some Font Family", monospace
```

## Further Reading

* [stylelint - font-family-no-duplicate-names](https://stylelint.io/user-guide/rules/font-family-no-duplicate-names)