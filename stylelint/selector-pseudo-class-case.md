Pattern: Inconsistent pseudo-class selector case

Issue: -

## Description

Specify lowercase or uppercase for pseudo-class selectors.

## Examples

### `"lower"`

The following patterns are considered violations:

```css
a:Hover {}
```

```css
a:hOvEr {}
```

```css
a:HOVER {}
```

```css
:ROOT {}
```

```css
:-MS-INPUT-PLACEHOLDER {}
```

The following patterns are *not* considered violations:

```css
a:hover {}
```

```css
:root {}
```

```css
:-ms-input-placeholder {}
```

### `"upper"`

The following patterns are considered violations:

```css
a:Hover {}
```

```css
a:hOvEr {}
```

```css
a:hover {}
```

```css
:root {}
```

```css
:-ms-input-placeholder {}
```

The following patterns are *not* considered violations:

```css
a:HOVER {}
```

```css
:ROOT {}
```

```css
:-MS-INPUT-PLACEHOLDER {}
```

## Further Reading

* [stylelint - selector-pseudo-class-case](https://stylelint.io/user-guide/rules/selector-pseudo-class-case)