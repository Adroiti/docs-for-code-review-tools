Pattern: Malformed combinator nesting in selector

Issue: -

## Description

Require or disallow nesting of combinators in selectors.

Examples of selectors without nesting of combinators:

```scss
.foo .bar {}

.foo.bar {}

.foo > .bar {}

.foo:hover {}
```

Corresponding selectors with combinators nested:

```scss
.foo {
  .bar {}
}

.foo {
  &.bar {}
}

.foo {
  & > .bar {}
}

.foo {
  &:hover {}
}
```

## Further Reading

* [stylelint-scss - selector-nest-combinators](https://github.com/kristerkari/stylelint-scss/tree/master/src/rules/selector-nest-combinators)