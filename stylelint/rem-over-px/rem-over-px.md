Pattern: Use of `px` unit

Issue: -

## Description

Enforce the usage of rem units over px units. It can also be used to migrate a project that uses px to use rem.

## Examples

```css
width: 8px; // error -> can be autofixed to width: 0.5rem;
height: 1.5rem; // ok
border: 1px solid #000000; // ok
border: 2px solid #000000; // error -> can be autofixed to width: 0.125rem;
@media (max-width: 768px) { display: none }; // ok
background-image: url('https://exapmle.com?size=500pxX500px'); // ok
```


## Further Reading

* [stylelint-rem-over-px](https://github.com/a-tokyo/stylelint-rem-over-px)