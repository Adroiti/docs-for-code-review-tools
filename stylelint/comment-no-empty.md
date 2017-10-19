Pattern: Empty CSS comment

Issue: -

## Description

Disallow empty comments. 

**Caveat:** Comments within *selector and value lists* are currently ignored.

## Examples

The following patterns are considered violations:

```css
    /* */
/** ↑
 * Comments like this */
```

```css
/**/
```

```css
/*

 */
```

The following patterns are *not* considered violations:

```css
/* comment */
```

```css
/*
 * Multi-line Comment
**/
```

## Further Reading

* [stylelint - comment-no-empty](https://stylelint.io/user-guide/rules/comment-no-empty)