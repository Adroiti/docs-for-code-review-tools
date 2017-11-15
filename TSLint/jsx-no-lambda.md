Pattern: Lambda in JSX attribute

Issue: -

## Description

Checks for fresh lambda literals used in JSX attributes.

Creating new anonymous functions (with either the `function` syntax or ES2015 arrow syntax) inside the `render` call stack works against pure component rendering. When doing an equality check between two lambdas, React will always consider them unequal values and force the component to re-render more often than necessary.

Example of **incorrect** code:

```ts
export const someButton = (
    <button onClick={() => console.log("clicked")}>
                     ~~~~~~~~~~~~~~~~~~~~~~~~~~~~
        Log something
    </button>
);
```

Example of **correct** code:

```ts
export const someButton = (
    <button onClick={handleClick}>
        Log something
    </button>
);
```