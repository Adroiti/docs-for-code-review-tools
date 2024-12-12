Pattern: Malformed case for pseudo-class

Issue: -

## Description

Specify lowercase or uppercase for pseudo-class selectors.

```css
  a:hover {}
/** ↑
 * This pseudo-class selector */
```

## Examples

`string`: `"lower"|"upper"`

### `"lower"`

The following patterns are considered problems:

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

The following patterns are _not_ considered problems:

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

The following patterns are considered problems:

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

The following patterns are _not_ considered problems:

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