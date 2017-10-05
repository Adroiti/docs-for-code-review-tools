Pattern: Misaligned parameter of multi-line method call

Issue: -

## Description

Function parameters should be aligned vertically if they're in multiple lines in a method call.

Examples of **correct** code:
```swift
foo(param1: 1, param2: bar
    param3: false, param4: true)


foo(param1: 1, param2: bar)


foo(param1: 1, param2: bar
    param3: false,
    param4: true)


foo(
   param1: 1
) { _ in }


UIView.animate(withDuration: 0.4, animations: {
    blurredImageView.alpha = 1
}, completion: { _ in
    self.hideLoading()
})


UIView.animate(withDuration: 0.4, animations: {
    blurredImageView.alpha = 1
},
completion: { _ in
    self.hideLoading()
})


foo(param1: 1, param2: { _ in },
    param3: false, param4: true)


foo({ _ in
       bar()
   },
   completion: { _ in
       baz()
   }
)


foo(param1: 1, param2: [
   0,
   1
], param3: 0)

```
Examples of **incorrect** code:
```swift

foo(param1: 1, param2: bar
                ↓param3: false, param4: true)


foo(param1: 1, param2: bar
 ↓param3: false, param4: true)


foo(param1: 1, param2: bar
       ↓param3: false,
       ↓param4: true)


foo(param1: 1,
       ↓param2: { _ in })


foo(param1: 1,
    param2: { _ in
}, param3: 2,
 ↓param4: 0)


foo(param1: 1, param2: { _ in },
       ↓param3: false, param4: true)

```

## Further Reading

* [SwiftLint - Vertical Parameter Alignment On Call](https://github.com/realm/SwiftLint/blob/master/Rules.md#vertical-parameter-alignment-on-call)