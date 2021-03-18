Pattern: Non-private Combine subject

Issue: -

## Description

Combine Subject should be private.

Examples of **correct** code:

```swift
final class Foobar {
    private let goodSubject = PassthroughSubject<Bool, Never>()
}

final class Foobar {
    private let goodSubject: PassthroughSubject<Bool, Never>
}

final class Foobar {
    fileprivate let goodSubject: PassthroughSubject<Bool, Never>
}

final class Foobar {
    private let goodSubject: PassthroughSubject<Bool, Never> = .ini()
}

final class Foobar {
    private let goodSubject = CurrentValueSubject<Bool, Never>(false)
}

final class Foobar {
    private let goodSubject: CurrentValueSubject<Bool, Never>
}

final class Foobar {
    fileprivate let goodSubject: CurrentValueSubject<String, Never>
}

final class Foobar {
    private let goodSubject: CurrentValueSubject<String, Never> = .ini("toto")
}

final class Foobar {
    private let goodSubject = PassthroughSubject<Set<String>, Never>()
}

final class Foobar {
    private let goodSubject: PassthroughSubject<Set<String>, Never> = .init()
}

final class Foobar {
    private let goodSubject: CurrentValueSubject<Set<String>, Never> = .init([])
}

final class Foobar {
    private let goodSubject =
        PassthroughSubject<Bool, Never>()
}

final class Foobar {
    private let goodSubject:
        PassthroughSubject<Bool, Never> = .ini()
}

final class Foobar {
    private let goodSubject =
        CurrentValueSubject<Bool, Never>(true)
}

```

Examples of **incorrect** code:

```swift
final class Foobar {
    let ↓badSubject = PassthroughSubject<Bool, Never>()
}

final class Foobar {
    let ↓badSubject: PassthroughSubject<Bool, Never>
}

final class Foobar {
    private(set) let ↓badSubject: PassthroughSubject<Bool, Never>
}

final class Foobar {
    private(set) let ↓badSubject = PassthroughSubject<Bool, Never>()
}

final class Foobar {
    let goodSubject: PassthroughSubject<Bool, Never> = .ini()
}

final class Foobar {
    private let goodSubject: PassthroughSubject<Bool, Never>
    private(set) let ↓badSubject = PassthroughSubject<Bool, Never>()
    private(set) let ↓anotherBadSubject = PassthroughSubject<Bool, Never>()
}

final class Foobar {
    private(set) let ↓badSubject = PassthroughSubject<Bool, Never>()
    private let goodSubject: PassthroughSubject<Bool, Never>
    private(set) let ↓anotherBadSubject = PassthroughSubject<Bool, Never>()
}

final class Foobar {
    let ↓badSubject = CurrentValueSubject<Bool, Never>(true)
}

final class Foobar {
    let ↓badSubject: CurrentValueSubject<Bool, Never>
}

final class Foobar {
    private(set) let ↓badSubject: CurrentValueSubject<Bool, Never>
}

final class Foobar {
    private(set) let ↓badSubject = CurrentValueSubject<Bool, Never>(false)
}

final class Foobar {
    let goodSubject: CurrentValueSubject<String, Never> = .ini("toto")
}

final class Foobar {
    private let goodSubject: CurrentValueSubject<Bool, Never>
    private(set) let ↓badSubject = CurrentValueSubject<Bool, Never>(false)
    private(set) let ↓anotherBadSubject = CurrentValueSubject<Bool, Never>(false)
}

final class Foobar {
    private(set) let ↓badSubject = CurrentValueSubject<Bool, Never>(false)
    private let goodSubject: CurrentValueSubject<Bool, Never>
    private(set) let ↓anotherBadSubject = CurrentValueSubject<Bool, Never>(true)
}

final class Foobar {
    let ↓badSubject = PassthroughSubject<Set<String>, Never>()
}

final class Foobar {
    let ↓badSubject: PassthroughSubject<Set<String>, Never> = .init()
}

final class Foobar {
    let ↓badSubject: CurrentValueSubject<Set<String>, Never> = .init([])
}

final class Foobar {
    let ↓badSubject =
        PassthroughSubject<Bool, Never>()
}

final class Foobar {
    let ↓badSubject:
        PassthroughSubject<Bool, Never> = .ini()
}

final class Foobar {
    let ↓badSubject =
        CurrentValueSubject<Bool, Never>(true)
}

```

## Further Reading

* [SwiftLint - Private Combine Subject](https://realm.github.io/SwiftLint/private_subject.html)