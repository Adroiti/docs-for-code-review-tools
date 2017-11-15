Pattern: Function binding in JSX attribute

Issue: -

## Description

Forbids function binding in JSX attributes. This has the same intent as `jsx-no-lambda` in helping you avoid excessive re-renders.

Note that this currently only does a simple _syntactic_ check, not a _semantic_ one (it doesn't use the type checker). So it may have some rare false positives if you define your own `.bind` function and supply `this` as a parameter.

Example of **incorrect** code:

```ts
export const selector = (
    <Component
        prop1={this.state.availableColumns}
        prop2={this.onChangeHandler.bind(this)}
               ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
        prop3={this.state.stateVar1}
    />
);
```

Example of **correct** code:

```ts
export const selector = (
    <Component
        prop1={this.state.availableColumns}
        prop3={this.state.stateVar1}
    />
);
```