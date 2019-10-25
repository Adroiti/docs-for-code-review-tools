Pattern: Malformed empty line before non-nested rule

Issue: -

## Description

Require or disallow an empty line before non-nested rules.

```css
a {}
      /* ← */
b {}  /* ↑ */
/**      ↑
 * This line */
```

If the rule is the very first node in a stylesheet then it is ignored.

## Examples

`string`: `"always"|"never"|"always-multi-line"|"never-multi-line"`

### `"always"`

There *must always* be an empty line before rules.

The following patterns are considered warnings:

```css
a {} b {}
```

```css
a {}
b {}
```

The following patterns are *not* considered warnings:

```css
a {}

b {}
```

### `"never"`

There *must never* be an empty line before rules.

The following patterns are considered warnings:

```css
a {}

b {}
```

The following patterns are *not* considered warnings:

```css
a {} b {}
```

```css
a {}
b {}
```

### `"always-multi-line"`

There *must always* be an empty line before multi-line rules.

The following patterns are considered warnings:

```css
a
{}
b
{}
```

The following patterns are *not* considered warnings:

```css
a
{}

b
{}
```

### `"never-multi-line"`

There *must never* be an empty line before multi-line rules.

The following patterns are considered warnings:

```css
a
{}

b
{}
```

The following patterns are *not* considered warnings:

```css
a
{}
b
{}
```