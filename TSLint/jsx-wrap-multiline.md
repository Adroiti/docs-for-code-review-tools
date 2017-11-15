Pattern: Malformed multi-line JSX element wrapping

Issue: -

## Description

Enforces that multi-line JSX elements are wrapped with parentheses. Opening parenthesis must be followed by a newline, closing parenthesis must be preceded by a newline.

Example of **incorrect** code:

```ts
const button = <button type="submit">
    Submit
</button>;
```

Example of **correct** code:

```ts
const button = (
    <button type="submit">
        Submit
    </button>
);
```