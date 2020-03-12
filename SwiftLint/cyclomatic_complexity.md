Pattern: Cyclomatic complexity is too high

Issue: -

## Description

Complexity of function bodies should be limited.

Examples of **correct** code:
```swift
func f1() {
if true {
for _ in 1..5 { } }
if false { }
}


func f(code: Int) -> Int {switch code {
 case 0: fallthrough
case 0: return 1
case 0: return 1
case 0: return 1
case 0: return 1
case 0: return 1
case 0: return 1
case 0: return 1
case 0: return 1
default: return 1}}


func f1() {if true {}; if true {}; if true {}; if true {}; if true {}; if true {}
func f2() {
if true {}; if true {}; if true {}; if true {}; if true {}
}}

```
Examples of **incorrect** code:
```swift

↓func f1() {
  if true {
    if true {
      if false {}
    }
  }
  if false {}
  let i = 0

  switch i {
  case 1: break
  case 2: break
  case 3: break
  case 4: break
 default: break
  }
  for _ in 1...5 {
    guard true else {
      return
    }
  }
}

```

## Further Reading

* [SwiftLint - Cyclomatic Complexity](https://realm.github.io/SwiftLint/cyclomatic_complexity.html)