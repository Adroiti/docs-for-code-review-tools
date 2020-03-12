Pattern: Missing use of shorthand operator

Issue: -

## Description

Prefer shorthand operators (+=, -=, *=, /=) over doing the operation and assigning.

Examples of **correct** code:
```swift
foo -= 1


foo -= variable


foo -= bar.method()


self.foo = foo - 1


foo = self.foo - 1


page = ceilf(currentOffset - pageWidth)


foo = aMethod(foo - bar)


foo = aMethod(bar - foo)


foo /= 1


foo /= variable


foo /= bar.method()


self.foo = foo / 1


foo = self.foo / 1


page = ceilf(currentOffset / pageWidth)


foo = aMethod(foo / bar)


foo = aMethod(bar / foo)


foo += 1


foo += variable


foo += bar.method()


self.foo = foo + 1


foo = self.foo + 1


page = ceilf(currentOffset + pageWidth)


foo = aMethod(foo + bar)


foo = aMethod(bar + foo)


foo *= 1


foo *= variable


foo *= bar.method()


self.foo = foo * 1


foo = self.foo * 1


page = ceilf(currentOffset * pageWidth)


foo = aMethod(foo * bar)


foo = aMethod(bar * foo)


var helloWorld = "world!"
 helloWorld = "Hello, " + helloWorld


angle = someCheck ? angle : -angle


seconds = seconds * 60 + value

```
Examples of **incorrect** code:
```swift

↓foo = foo - 1


↓foo = foo - aVariable


↓foo = foo - bar.method()


↓foo.aProperty = foo.aProperty - 1


↓self.aProperty = self.aProperty - 1


↓foo = foo / 1


↓foo = foo / aVariable


↓foo = foo / bar.method()


↓foo.aProperty = foo.aProperty / 1


↓self.aProperty = self.aProperty / 1


↓foo = foo + 1


↓foo = foo + aVariable


↓foo = foo + bar.method()


↓foo.aProperty = foo.aProperty + 1


↓self.aProperty = self.aProperty + 1


↓foo = foo * 1


↓foo = foo * aVariable


↓foo = foo * bar.method()


↓foo.aProperty = foo.aProperty * 1


↓self.aProperty = self.aProperty * 1


n = n + i / outputLength


n = n - i / outputLength

```

## Further Reading

* [SwiftLint - Shorthand Operator](https://realm.github.io/SwiftLint/shorthand_operator.html)