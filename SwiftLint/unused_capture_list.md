Pattern: Unused reference in capture list

Issue: -

## Description

Unused reference in a capture list should be removed.

Examples of **correct** code:

```swift
[1, 2].map { [weak self] num in
    self?.handle(num)
}


let failure: Failure = { [weak self, unowned delegate = self.delegate!] foo in
    delegate.handle(foo, self)
}


numbers.forEach({
    [weak handler] in
    handler?.handle($0)
})


withEnvironment(apiService: MockService(fetchProjectResponse: project)) {
    [Device.phone4_7inch, Device.phone5_8inch, Device.pad].forEach { device in
        device.handle()
    }
}


{ [foo] _ in foo.bar() }()


sizes.max().flatMap { [(offset: offset, size: $0)] } ?? []

```
Examples of **incorrect** code:
```swift

[1, 2].map { [↓weak self] num in
    print(num)
}


let failure: Failure = { [weak self, ↓unowned delegate = self.delegate!] foo in
    self?.handle(foo)
}


let failure: Failure = { [↓weak self, ↓unowned delegate = self.delegate!] foo in
    print(foo)
}


numbers.forEach({
    [weak handler] in
    print($0)
})


withEnvironment(apiService: MockService(fetchProjectResponse: project)) { [↓foo] in
    [Device.phone4_7inch, Device.phone5_8inch, Device.pad].forEach { device in
        device.handle()
    }
}


{ [↓foo] in _ }()

```

## Further Reading

* [SwiftLint - Unused Capture List](https://github.com/realm/SwiftLint/blob/master/Rules.md#unused-capture-list)