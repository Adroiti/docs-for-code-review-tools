Pattern: Inconsistent pseudo-element selector case

Issue: -

## Description

Specify lowercase or uppercase for pseudo-element selectors.

## Examples

### `"lower"`

The following patterns are considered violations:

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

The following patterns are *not* considered violations:

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

The following patterns are considered violations:

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

The following patterns are *not* considered violations:

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