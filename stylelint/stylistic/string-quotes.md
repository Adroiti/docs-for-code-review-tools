Pattern: Malformed quotes around string

Issue: -

## Description

Specify single or double quotes around strings. Quotes within comments are ignored.

```css
/* "This is fine" */
/* 'And this is also fine' */
```

Single quotes in a charset @-rule are ignored as using single quotes in this context is incorrect according the [CSS specification](https://www.w3.org/TR/CSS2/syndata.html#x57).

```css
@charset "utf-8"
/* fine regardless of configuration */
```

## Examples

### `"single"`

Strings *must always* be wrapped with single quotes.

The following patterns are considered violations:

```css
a { content: "x"; }
```

```css
a[id="foo"] {}
```

The following patterns are *not* considered violations:

```css
a { content: 'x'; }
```

```css
a[id='foo'] {}
```

### `"double"`

Strings *must always* be wrapped with double quotes.

The following patterns are considered violations:

```css
a { content: 'x'; }
```

```css
a[id='foo'] {}
```

The following patterns are *not* considered violations:

```css
a { content: "x"; }
```

```css
a[id="foo"] {}
```

## Further Reading

* [stylelint - string-quotes](https://github.com/stylelint-stylistic/stylelint-stylistic/tree/main/lib/rules/string-quotes)