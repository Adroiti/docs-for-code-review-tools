Pattern: Misaligned multi-line elements

Issue: -

## Description

Enforces a consistent style for multi-line JSX elements which promotes ease of editing via line-wise manipulations as well as maintainability via small diffs when changes are made.

Example of **incorrect** code:

```ts
const element = <Tag className="test"
                 ~~~ [JSX attributes must be on a line below the opening tag]
                 tabIndex={1}
/>;
```

Example of **correct** code:

```ts
const element = <div
    className="test"
    tabIndex={1}
>
    {children}
</div>;
```