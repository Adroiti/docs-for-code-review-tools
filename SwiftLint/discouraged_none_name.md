Pattern: Use of `none` name

Issue: -

## Description

Discourages name cases/static members `none`, which can conflict with `Optional<T>.none`.

Examples of **correct** code:

```swift
enum TestEnum {
    case nOne
}
```

Examples of **incorrect** code:
```swift
enum TestEnum {
    case ↓none
}
```

## Further Reading

* [SwiftLint - Discouraged None Name](https://realm.github.io/SwiftLint/discouraged_none_name.html)