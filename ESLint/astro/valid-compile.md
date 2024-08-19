Pattern: Unresolved compile warning

Issue: -

## Description

Disallow warnings when compiling.

## Examples

Example of **incorrect** code:

```astro
---
let string = "Foo"
---

<p set:text="string">string</p>
<p set:text={string}>{string}</p>
<p set:text={string}>string</p>
<p set:text="string">{string}</p>
<button set:text="string">
  <div></div>
</button>
<button set:text="string">
  <div>Foo</div>{string}
</button>
<p set:text="string">
  <!-- comment -->{string}
</p>
```

Example of **correct** code:

```astro
---
let string = "Foo"
---

<p></p>
<p>string</p>
<p>{string}</p>
<p>
  <!-- comment -->{string}
</p>
<div><p></p></div>
```
