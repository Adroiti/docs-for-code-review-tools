Pattern: Unused `define:vars={...}` in `style` tag

Issue: -

## Description

Disallow unused `define:vars={...}` in `style` tag.

## Examples

Example of **incorrect** code:

```astro
---
const foregroundColor = "rgb(221 243 228)"
const backgroundColor = "rgb(24 121 78)"
---

<style define:vars={{ foregroundColor, backgroundColor }}>
  h1 {
    background-color: var(--background);
    color: var(--foreground);
  }
</style>
<h1>Hello</h1>
```

Example of **correct** code:

```astro
---
const foregroundColor = "rgb(221 243 228)"
const backgroundColor = "rgb(24 121 78)"
---

<style define:vars={{ foregroundColor, backgroundColor }}>
  h1 {
    background-color: var(--backgroundColor);
    color: var(--foregroundColor);
  }
</style>
<h1>Hello</h1>
```
