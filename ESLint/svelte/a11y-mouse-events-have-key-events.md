Pattern: Missing key event for mouse event

Issue: -

## Description

Enforce that `on:mouseover` and `on:mouseout` are accompanied by `on:focus` and `on:blur`, respectively. This helps to ensure that any functionality triggered by these mouse events is also accessible to keyboard users.

```sv
<!-- A11y: on:mouseover must be accompanied by on:focus -->
<div on:mouseover={handleMouseover} />

<!-- A11y: on:mouseout must be accompanied by on:blur -->
<div on:mouseout={handleMouseout} />
```

## Further Reading

* [ESLint - a11y-mouse-events-have-key-events](https://svelte.dev/docs#accessibility-warnings-a11y-mouse-events-have-key-events)