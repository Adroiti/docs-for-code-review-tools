Pattern: Fall-through in `switch` statement

Issue: -

## Description

Fall-through in switch statements is often unintentional and a bug.

For example, the following is not allowed:

```ts
switch(foo) {
    case 1:
        someFunc(foo);
    case 2:
        someOtherFunc(foo);
}
```

However, fall through is allowed when case statements are consecutive or a magic `/* falls through */` comment is present. The following is valid:

```ts
switch(foo) {
    case 1:
        someFunc(foo);
        /* falls through */
    case 2:
    case 3:
        someOtherFunc(foo);
}
```

## Further Reading

* [TSLint - no-switch-case-fall-through](https://palantir.github.io/tslint/rules/no-switch-case-fall-through)