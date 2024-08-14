Pattern: Missing `width`/`height` for `<img>`

Issue: -

## Description

For performance reasons, always provide width and height attributes for `<img>` elements, it will help to prevent layout shifts.

## Examples

Example of **incorrect** code:

```jsx
<img src="/static/images/portrait-01.webp">
```

Example of **correct** code:

```jsx
<img width="200" height="600" src="/static/images/portrait-01.webp">
```
