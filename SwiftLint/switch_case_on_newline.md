Pattern: Malformed `case` inside `switch`

Issue: -

## Description

Cases inside a `switch` should always be on a newline.

Examples of **correct** code:
```swift
/*case 1: */return true


//case 1:
 return true


let x = [caseKey: value]


let x = [key: .default]


if case let .someEnum(value) = aFunction([key: 2]) { }


guard case let .someEnum(value) = aFunction([key: 2]) { }


for case let .someEnum(value) = aFunction([key: 2]) { }


enum Environment {
 case development
}


enum Environment {
 case development(url: URL)
}


enum Environment {
 case development(url: URL) // staging
}


switch foo {
  case 1:
 return true
}


switch foo {
  default:
 return true
}


switch foo {
  case let value:
 return true
}


switch foo {
  case .myCase: // error from network
 return true
}


switch foo {
  case let .myCase(value) where value > 10:
 return false
}


switch foo {
  case let .myCase(value)
 where value > 10:
 return false
}


switch foo {
  case let .myCase(code: lhsErrorCode, description: _)
 where lhsErrorCode > 10:
 return false
}


switch foo {
  case #selector(aFunction(_:)):
 return false

}

```
Examples of **incorrect** code:
```swift

switch foo {
  ↓case 1: return true
}


switch foo {
  ↓case let value: return true
}


switch foo {
  ↓default: return true
}


switch foo {
  ↓case "a string": return false
}


switch foo {
  ↓case .myCase: return false // error from network
}


switch foo {
  ↓case let .myCase(value) where value > 10: return false
}


switch foo {
  ↓case #selector(aFunction(_:)): return false

}


switch foo {
  ↓case let .myCase(value)
 where value > 10: return false
}


switch foo {
  ↓case .first,
 .second: return false
}

```

## Further Reading

* [SwiftLint - Switch Case on Newline](https://realm.github.io/SwiftLint/switch_case_on_newline.html)