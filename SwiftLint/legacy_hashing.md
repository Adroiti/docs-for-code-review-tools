Pattern: Use of legacy hashing

Issue: -

## Description

Prefer using the `hash(into:)` function instead of overriding `hashValue`.

Examples of **correct** code:
```swift
struct Foo: Hashable {
  let bar: Int = 10

  func hash(into hasher: inout Hasher) {
    hasher.combine(bar)
  }
}


class Foo: Hashable {
  let bar: Int = 10

  func hash(into hasher: inout Hasher) {
    hasher.combine(bar)
  }
}


var hashValue: Int { return 1 }
class Foo: Hashable { 
 }


class Foo: Hashable {
  let bar: String = "Foo"

  public var hashValue: String {
    return bar
  }
}


class Foo: Hashable {
  let bar: String = "Foo"

  public var hashValue: String {
    get { return bar }
    set { bar = newValue }
  }
}

```
Examples of **incorrect** code:
```swift

struct Foo: Hashable {
    let bar: Int = 10

    public ↓var hashValue: Int {
        return bar
    }
}


class Foo: Hashable {
    let bar: Int = 10

    public ↓var hashValue: Int {
        return bar
    }
}

```

## Further Reading

* [SwiftLint - Legacy Hashing](https://github.com/realm/SwiftLint/blob/master/Rules.md#legacy-hashing)