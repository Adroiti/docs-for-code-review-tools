Pattern: Use of `&` in union class name

Issue: -

## Description

Disallow union class names with the parent selector (`&`).

```scss
.class {
  &-union {
//↑
// This type usage of `&`
  }
}
```

The following patterns are considered warnings:

```scss
.class {
  &-union {}
}
```

```scss
.class {
  &_union {}
}
```

```scss
.class {
  &union {}
}
```

The following patterns are *not* considered warnings:

```scss
.class {
  &.foo {}
}
```

```scss
.class {
  & p {}
}
```

## Further Reading

* [stylelint - selector-no-union-class-name](https://stylelint.io/user-guide/rules/selector-no-union-class-name)