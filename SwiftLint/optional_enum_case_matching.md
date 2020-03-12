Pattern: Unsupported optional enum case matching

Issue: -

## Description

Matching an enum case against an optional enum without `?` is supported on _Swift 5.1_ and above.

Examples of **correct** code:

```swift
switch foo {
 case .bar: break
 case .baz: break
 default: break
}

switch foo {
 case (.bar, .baz): break
 case (.bar, _): break
 case (_, .baz): break
 default: break
}
```

Examples of **incorrect** code:

```swift
switch foo {
 case .bar↓?: break
 case .baz: break
 default: break
}

switch foo {
 case Foo.bar↓?: break
 case .baz: break
 default: break
}

switch foo {
 case .bar↓?, .baz↓?: break
 default: break
}

switch foo {
 case .bar↓? where x > 1: break
 case .baz: break
 default: break
}

switch foo {
 case (.bar↓?, .baz↓?): break
 case (.bar↓?, _): break
 case (_, .bar↓?): break
 default: break
}
```

## Further Reading

* [SwiftLint - Optional Enum Case Match](https://realm.github.io/SwiftLint/optional_enum_case_matching.html)