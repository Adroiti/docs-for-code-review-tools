Pattern: Use of multi-line JS expression

Issue: -

## Description

Disallows multi-line JS expressions inside JSX blocks to promote readability.

Example of **incorrect** code:

```ts
const htmlBadStr = <div
    className="my-class"
>
    {test ?
    ~~~~~~~
        children
~~~~~~~~~~~~~~~~
    }
~~~~~ [Multiline JS expressions inside JSX are forbidden]
</div>;
```

Example of **correct** code:

```ts
const htmlStr = <div
    className="my-class"
    tabIndex={-1}
>
    {children}
</div>;
```