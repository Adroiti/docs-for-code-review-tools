Pattern: Unowned variable capture

Issue: -

## Description

Prefer capturing references as weak to avoid potential crashes.

Examples of **correct** code:

```swift
foo { [weak self] in _ }


foo { [weak self] param in _ }


foo { [weak bar] in _ }


foo { [weak bar] param in _ }


foo { bar in _ }


foo { $0 }

```

Examples of **incorrect** code:

```swift

foo { [↓unowned self] in _ }


foo { [↓unowned bar] in _ }


foo { [bar, ↓unowned self] in _ }

```

## Further Reading

* [SwiftLint - Unowned Variable Capture](https://realm.github.io/SwiftLint/unowned_variable_capture.html)