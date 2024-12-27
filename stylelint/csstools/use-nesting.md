Pattern: Missing use of nesting

Issue: -

## Description

Enforces nesting when it is possible in CSS.

## Examples

### always

If the first option is `"always"` or `true`, then [Stylelint Use Nesting]
requires all nodes to be linted, and the following patterns are _not_
considered violations:

```pcss
.example {
  color: blue;

  &:hover {
    color: rebeccapurple;
  }
}
```

```pcss
.example {
  color: blue;

  @media (min-width: 640px) {
    color: rebeccapurple;
  }
}
```

While the following patterns are considered violations:

```pcss
.example {
  color: blue;
}

.example:hover {
  color: rebeccapurple;
}
```

```pcss
.example {
  color: blue;
}

@media (min-width: 640px) {
  .example {
    color: rebeccapurple;
  }
}
```

## Further Reading

* [stylelint-use-nesting](https://github.com/csstools/stylelint-use-nesting)