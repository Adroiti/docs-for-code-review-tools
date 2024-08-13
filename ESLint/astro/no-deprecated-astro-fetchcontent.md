Pattern: Use of deprecated `Astro.fetchContent()`

Issue: -

## Description

Disallow using deprecated `Astro.fetchContent()`.

Example of **incorrect** code:

```astro
let allPosts = Astro.fetchContent('./posts/*.md');
```

Example of **correct** code:

```astro
let allPosts = await Astro.glob('./posts/*.md');
```
