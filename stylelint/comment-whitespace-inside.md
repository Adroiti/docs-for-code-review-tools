Pattern: Malformed whitespace for comment marker

Issue: -

## Description

Require or disallow whitespace on the inside of comment markers. Any number of asterisks are allowed at the beginning or end of the comment. So `/** comment **/` is treated the same way as `/* comment */`.

**Caveat:** Comments within *selector and value lists* are currently ignored.

## Examples

### `"always"`

There *must always* be whitespace inside the markers.

The following patterns are considered violations:

```css
/*comment*/
```

```css
/*comment */
```

```css
/** comment**/
```

The following patterns are *not* considered violations:

```css
/* comment */
```

```css
/** comment **/
```

```css
/**
 * comment
 */
```

```css
/*     comment
*/
```

### `"never"`

There *must never* be whitespace on the inside the markers.

The following patterns are considered violations:

```css
/* comment */
```

```css
/*comment */
```

```css
/** comment**/
```

The following patterns are *not* considered violations:

```css
/*comment*/
```

```css
/****comment****/
```

## Further Reading

* [stylelint - comment-whitespace-inside](https://stylelint.io/user-guide/rules/comment-whitespace-inside)