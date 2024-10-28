Pattern: Use of deprecated `getEntryBySlug()`

Issue: -

## Description

Disallow using deprecated `getEntryBySlug()`.

## Examples

```astro
---
/* eslint astro/no-deprecated-getentrybyslug: "error" */

/* ✓ GOOD */
import { getEntry } from "astro:content";

/* ✗ BAD */
import { getEntryBySlug } from "astro:content";
---
```