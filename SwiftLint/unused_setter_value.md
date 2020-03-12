Pattern: Unused setter value

Issue: -

## Description

Warns if setter value is not used.

Examples of **correct** code:

```swift
var aValue: String {
    get {
        return Persister.shared.aValue
    }
    set {
        Persister.shared.aValue = newValue
    }
}


var aValue: String {
    set {
        Persister.shared.aValue = newValue
    }
    get {
        return Persister.shared.aValue
    }
}


var aValue: String {
    get {
        return Persister.shared.aValue
    }
    set(value) {
        Persister.shared.aValue = value
    }
}

```
Examples of **incorrect** code:

```swift

var aValue: String {
    get {
        return Persister.shared.aValue
    }
    ↓set {
        Persister.shared.aValue = aValue
    }
}


var aValue: String {
    ↓set {
        Persister.shared.aValue = aValue
    }
    get {
        return Persister.shared.aValue
    }
}


var aValue: String {
    get {
        return Persister.shared.aValue
    }
    ↓set {
        Persister.shared.aValue = aValue
    }
}


var aValue: String {
    get {
        let newValue = Persister.shared.aValue
        return newValue
    }
    ↓set {
        Persister.shared.aValue = aValue
    }
}


var aValue: String {
    get {
        return Persister.shared.aValue
    }
    ↓set(value) {
        Persister.shared.aValue = aValue
    }
}

```

## Further Reading

* [SwiftLint - Unused Setter Value](https://realm.github.io/SwiftLint/unused_setter_value.html)