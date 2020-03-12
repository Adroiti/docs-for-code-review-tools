Pattern: Malformed closure end indentation

Issue: -

## Description

Closure end should have the same indentation as the line that started it.

Examples of **correct** code:
```swift
SignalProducer(values: [1, 2, 3])
   .startWithNext { number in
       print(number)
   }


[1, 2].map { $0 + 1 }


return match(pattern: pattern, with: [.comment]).flatMap { range in
   return Command(string: contents, range: range)
}.flatMap { command in
   return command.expand()
}


foo(foo: bar,
    options: baz) { _ in }


someReallyLongProperty.chainingWithAnotherProperty
   .foo { _ in }


foo(abc, 123)
{ _ in }

```
Examples of **incorrect** code:
```swift

SignalProducer(values: [1, 2, 3])
   .startWithNext { number in
       print(number)
↓}


return match(pattern: pattern, with: [.comment]).flatMap { range in
   return Command(string: contents, range: range)
   ↓}.flatMap { command in
   return command.expand()
↓}

```

## Further Reading

* [SwiftLint - Closure End Indentation](https://realm.github.io/SwiftLint/closure_end_indentation.html)