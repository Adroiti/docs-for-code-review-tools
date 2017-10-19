Pattern: Malformed quotation marks around font family name

Issue: -

## Description

This rule checks the `font` and `font-family` properties.

This rule ignores `$sass`, `@less`, and `var(--custom-property)` variable syntaxes.

## Examples

### `"always-unless-keyword"`

Expect quotes around every font family name that is not a keyword.

The following patterns are considered violations:

```css
a { font-family: Arial, sans-serif; }
```

```css
a { font-family: Times New Roman, Times, serif; }
```

```css
a { font: 1em Arial, sans-serif; }
```

The following patterns are *not* considered violations:

```css
a { font-family: 'Arial', sans-serif; }
```

```css
a { font-family: "Times New Roman", "Times", serif; }
```

```css
a { font: 1em 'Arial', sans-serif; }
```

### `"always-where-required"`

Expect quotes only when quotes are *required* according to the criteria above, and disallow quotes in all other cases.

The following patterns are considered violations:

```css
a { font-family: "Arial", sans-serif; }
```

```css
a { font-family: 'Times New Roman', Times, serif; }
```

```css
a { font: 1em "Arial", sans-serif; }
```

The following patterns are *not* considered violations:

```css
a { font-family: Arial, sans-serif; }
```

```css
a { font-family: Arial, sans-serif; }
```

```css
a { font-family: Times New Roman, Times, serif; }
```

```css
a { font-family: "Hawaii 5-0"; }
```

```css
a { font: 1em Arial, sans-serif; }
```

### `"always-where-recommended"`

Expect quotes only when quotes are *recommended* according to the criteria above, and disallow quotes in all other cases. (This includes all cases where quotes are *required*, as well.)

The following patterns are considered violations:

```css
a { font-family: Times New Roman, Times, serif; }
```

```css
a { font-family: MyFontVersion6, sake_case_font; }
```

```css
a { font-family: 'Arial', sans-serif; }
```

```css
a { font: 1em Times New Roman, Times, serif; }
```

The following patterns are *not* considered violations:

```css
a { font-family: 'Times New Roman', Times, serif; }
```

```css
a { font-family: "MyFontVersion6", "sake_case_font"; }
```

```css
a { font-family: Arial, sans-serif; }
```

```css
a { font: 1em 'Times New Roman', Times, serif; }
```

## Further Reading

* [stylelint - font-family-name-quotes](https://stylelint.io/user-guide/rules/font-family-name-quotes)