Pattern: Use of `!important` in declaration

Issue: -

## Description

This rule disallows `!important` within declarations.

If you always want `!important` in your declarations, e.g. if you're writing [user styles](https://userstyles.org/), you can *safely* add them using [`postcss-safe-important`](https://github.com/crimx/postcss-safe-important).

## Examples

The following patterns are considered violations:

```css
a { color: pink !important; }
/**             ↑
 * This !important */
```

```css
a { color: pink ! important; }
```

```css
a { color: pink!important; }
```

The following patterns are *not* considered violations:

```css
a { color: pink; }
```

## Further Reading

* [stylelint - declaration-no-important](https://stylelint.io/user-guide/rules/declaration-no-important)