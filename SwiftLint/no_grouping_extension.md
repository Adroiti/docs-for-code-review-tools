Pattern: Grouping code with extensions

Issue: -

## Description

Extensions shouldn't be used to group code within the same source file.

Examples of **correct** code:
```swift
protocol Food {}
extension Food {}


class Apples {}
extension Oranges {}

```
Examples of **incorrect** code:
```swift

enum Fruit {}
↓extension Fruit {}


↓extension Tea: Error {}
struct Tea {}


class Ham { class Spam {}}
↓extension Ham.Spam {}


extension External { struct Gotcha {}}
↓extension External.Gotcha {}

```

## Further Reading

* [SwiftLint - No Grouping Extension](https://github.com/realm/SwiftLint/blob/master/Rules.md#no-grouping-extension)