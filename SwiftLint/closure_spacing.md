Pattern: Malformed closure spacing

Issue: -

## Description

Closure expressions should have a single space inside each brace.

Examples of **correct** code:
```swift
[].map ({ $0.description })


[].filter { $0.contains(location) }


extension UITableViewCell: ReusableView { }


extension UITableViewCell: ReusableView {}

```
Examples of **incorrect** code:
```swift

[].filter(↓{$0.contains(location)})


[].map(↓{$0})


(↓{each in return result.contains(where: ↓{e in return e}) }).count


filter ↓{ sorted ↓{ $0 < $1}}

```

## Further Reading

* [SwiftLint - Closure Spacing](https://realm.github.io/SwiftLint/closure_spacing.html)