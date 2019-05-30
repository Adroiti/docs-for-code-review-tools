Pattern: Unmerged `if` statement

Issue: -

## Description

Identifies nested if statements that can be combined into one.

## Examples

Not passing:

```ts
/* 1 */
if (foo)
  if (bar);
/* 2 */
if (foo) {
  if (bar) {
  }
}
/* 3 */
if (foo) {
} else {
  if (bar) {
  } else {
  }
}
```

Passing:

```ts
/* 1 */
if (foo && bar);
/* 2 */
if (foo && bar) {
}
/* 3 */
if (foo) {
} else if (bar) {
} else {
}

if (foo) {
  if (bar) {
  } else {
  }
}

if (foo) {
  if (bar) {
  }
} else {
}
```

## Further Reading

* [TSLint - no-collapsible-if](https://github.com/ajafff/tslint-consistent-codestyle/blob/master/docs/no-collapsible-if.md)