Pattern: Yoda condition

Issue: -

## Description

The variable should be placed on the left, the constant on the right of a comparison operator.

Examples of **correct** code:
```swift
if foo == 42 {}


if foo <= 42.42 {}


guard foo >= 42 else { return }


guard foo != "str str" else { return }


while foo < 10 { }


while foo > 1 { }


while foo + 1 == 2


if optionalValue?.property ?? 0 == 2


if foo == nil

```
Examples of **incorrect** code:
```swift

↓if 42 == foo {}


↓if 42.42 >= foo {}


↓guard 42 <= foo else { return }


↓guard "str str" != foo else { return }


↓while 10 > foo { }


↓while 1 < foo { }


↓if nil == foo

```

## Further Reading

* [SwiftLint - Yoda condition rule](https://github.com/realm/SwiftLint/blob/master/Rules.md#yoda-condition-rule)