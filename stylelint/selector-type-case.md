Pattern: Inconsistent type selector case

Issue: -

## Description

Specify lowercase or uppercase for type selector.

## Examples

### `"lower"`

The following patterns are considered violations:

```css
A {}
```

```css
LI {}
```

The following patterns are *not* considered violations:

```css
a {}
```

```css
li {}
```

### `"upper"`

The following patterns are considered violations:

```css
a {}
```

```css
li {}
```

The following patterns are *not* considered violations:

```css
A {}
```

```css
LI {}
```

## Further Reading

* [stylelint - selector-type-case](https://stylelint.io/user-guide/rules/selector-type-case)