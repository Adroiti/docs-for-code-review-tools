Pattern: Missing punctuation for non-boolean media feature

Issue: -

## Description

Disallows missing punctuation for non-boolean media features.

```css
@media (max-width: 600px) {}
/**              ↑
 * This punctuation */
```

This rule ensures that there is either a colon or a range operator in non-boolean media features.

## Examples

The following patterns are considered warnings:

```css
@media (max-width 600px) {}
```

```css
@media (width   20em) {}
```

The following patterns are *not* considered warnings:

```css
@media (max-width: 600px) {}
```

```css
@media (width  >=  20em) {}
```
