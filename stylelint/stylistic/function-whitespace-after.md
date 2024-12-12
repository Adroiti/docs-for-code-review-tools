Pattern: Incorrect spacing after function

Issue: -

## Description

Require or disallow whitespace after functions.

```css
a { transform: translate(1, 1) scale(3); }
/**                           ↑
 *                   This space */
```

This rule does not check for space immediately after `)` if the very next character is `,`, `)`, `/` or `}`, allowing some of the patterns exemplified below.

## Examples

`string`: `"always"|"never"`

### `"always"`

There _must always_ be whitespace after the function.

The following patterns are considered problems:

```css
a { transform: translate(1, 1)scale(3); }
```

The following patterns are _not_ considered problems:

```css
a { transform: translate(1, 1) scale(3); }
```

```css
a { transform: translate(1, 1)     scale(3); }
```

```css
a {
  transform:
    translate(1, 1)
    scale(3);
}
```

```css
/* notice the two closing parentheses without a space between */
a { top: calc(1 * (1 + 3)); }
```

```css
/* notice the ), with no space after the closing parenthesis */
a { padding: calc(1 * 2px), calc(2 * 5px); }
```

### `"never"`

There _must never_ be whitespace after the function.

The following patterns are considered problems:

```css
a { transform: translate(1, 1) scale(3); }
```

The following patterns are _not_ considered problems:

```css
a { transform: translate(1, 1)scale(3); }
```

## Further Reading

* [stylelint - function-whitespace-after](https://stylelint.io/user-guide/rules/function-whitespace-after)