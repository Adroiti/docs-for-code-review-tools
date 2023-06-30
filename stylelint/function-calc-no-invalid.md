Pattern: Invalid expression within `calc` function

Issue: -

## Description

Disallow an invalid expression within `calc` functions.

## Examples

The following patterns are considered violations:

```css
.foo {width: calc();}
/**               ↑
 * empty expression */
.foo {width: calc(100% 80px);}
/**                   ↑
/* missing operator */
.foo {width: calc(100% -80px);}
/**                   ↑
/* missing operator */
.foo {width: calc(100% - - 80px);}
/**                      ↑
/* unexpected operator */
.foo {width: calc(100% -);}
/**                    ↑
/* unexpected operator */
.foo {width: calc(- 100%);}
/**               ↑
/* unexpected operator */
.foo {width: calc(100% / 0);}
/**                    ↑ ↑
/* division by zero */
.foo {width: calc(100px + 80);}
/**                  ↑  ↑  ↑
/* the `resolved type` is invalid */
.foo {width: calc(100% + 80);}
/**                  ↑ ↑  ↑
/* the `resolved type` is invalid */
.foo {width: calc(100px - 80);}
/**                  ↑  ↑  ↑
/* the `resolved type` is invalid */
.foo {width: calc(100px * 80px);}
/**                  ↑  ↑   ↑
/* the `resolved type` is invalid */
.foo {width: calc(100 / 80%);}
/**                 ↑ ↑   ↑
/* the `resolved type` is invalid */
```
