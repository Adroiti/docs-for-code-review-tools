Pattern: `!important` in a keyframe

Issue: -

## Description

Using `!important` within keyframes declarations is completely ignored in some browsers.

## Examples

The following patterns are considered violations:

```css
@keyframes important2 {
  from { margin: 10px }
  to { margin: 20px !important }
}                /* ↑ */
/**                 ↑
*     This !important */
```

```css
@keyframes important1 {
  from {
    margin-top: 50px;
  }
  to {
    margin-top: 100px!important;
  }
}
```

```css
@keyframes important1 {
  from {
    margin-top: 50px;
  }
  to {
    margin-top: 100px ! important;
  }
}
```

The following patterns are *not* considered violations:

```css
a { color: pink !important; }
```

```css
@keyframes important1 {
  from {
    margin-top: 50px;
  }
  to {
    margin-top: 100px;
  }
}
```

## Further Reading

* [MDN - !important in a keyframe](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes#!important_in_a_keyframe)
* [stylelint - keyframe-declaration-no-important](https://stylelint.io/user-guide/rules/keyframe-declaration-no-important)