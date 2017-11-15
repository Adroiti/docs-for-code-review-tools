Pattern: JSX element not self-closed

Issue: -

## Description

Enforces that JSX elements with no children are self-closing.

Example of **incorrect** code:

```ts
<div className="someValue"></div>
```

Example of **correct** code:

```ts
<div className="someValue" />
```