Pattern: Duplicate selector within keyframe block

Issue: -

## Description

Disallows duplicate selectors within keyframe blocks.

<!-- prettier-ignore -->
```css
@keyframes foo { 0% {} 0% {} }
/**                    ↑
 *                     This duplicate selector */
```

This rule is case-insensitive.

## Examples

The following patterns are considered problems:

<!-- prettier-ignore -->
```css
@keyframes foo { 0% {} 0% {} }
```

<!-- prettier-ignore -->
```css
@keyframes foo { from {} from {} }
```

<!-- prettier-ignore -->
```css
@keyframes foo { from {} FROM {} }
```

The following patterns are _not_ considered problems:

<!-- prettier-ignore -->
```css
@keyframes foo { 0% {} 100% {} }
```

<!-- prettier-ignore -->
```css
@keyframes foo { from {} to {} }
```

## Further Reading

* [stylelint - keyframe-block-no-duplicate-selectors](https://stylelint.io/user-guide/rules/list/keyframe-block-no-duplicate-selectors)