Pattern: Malformed enum case

Issue: -

## Description

Enums conforming to a specified protocol must implement a specific case(s).

Examples of **correct** code:
```swift
enum MyNetworkResponse: String, NetworkResponsable {
    case success, error, notConnected 
}


enum MyNetworkResponse: String, NetworkResponsable {
    case success, error, notConnected(error: Error) 
}


enum MyNetworkResponse: String, NetworkResponsable {
    case success
    case error
    case notConnected
}


enum MyNetworkResponse: String, NetworkResponsable {
    case success
    case error
    case notConnected(error: Error)
}

```
Examples of **incorrect** code:
```swift

enum MyNetworkResponse: String, NetworkResponsable {
    case success, error 
}


enum MyNetworkResponse: String, NetworkResponsable {
    case success, error 
}


enum MyNetworkResponse: String, NetworkResponsable {
    case success
    case error
}


enum MyNetworkResponse: String, NetworkResponsable {
    case success
    case error
}

```

## Further Reading

* [SwiftLint - Required Enum Case](https://github.com/realm/SwiftLint/blob/master/Rules.md#required-enum-case)