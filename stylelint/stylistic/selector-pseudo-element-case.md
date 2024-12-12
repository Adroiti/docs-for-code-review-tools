Pattern: Malformed case for pseudo-element

Issue: -

## Description

Specify lowercase or uppercase for pseudo-element selectors.

```css
  a::before {}
/**  ↑
 * This pseudo-element selector */
```

## Examples

`string`: `"lower"|"upper"`

### `"lower"`

The following patterns are considered problems:

```css
a:Before {}
```

```css
a:bEfOrE {}
```

```css
a:BEFORE {}
```

```css
a::Before {}
```

```css
a::bEfOrE {}
```

```css
a::BEFORE {}
```

```css
input::-MOZ-PLACEHOLDER {}
```

The following patterns are _not_ considered problems:

```css
a:before {}
```

```css
a::before {}
```

```css
input::-moz-placeholder {}
```

### `"upper"`

The following patterns are considered problems:

```css
a:Before {}
```

```css
a:bEfOrE {}
```

```css
a:BEFORE {}
```

```css
a::Before {}
```

```css
a::bEfOrE {}
```

```css
a::before {}
```

```css
input::-moz-placeholder {}
```

The following patterns are _not_ considered problems:

```css
a:BEFORE {}
```

```css
a::BEFORE {}
```

```css
input::-MOZ-PLACEHOLDER {}
```

## Further Reading

* [stylelint - selector-pseudo-element-case](https://stylelint.io/user-guide/rules/selector-pseudo-element-case)