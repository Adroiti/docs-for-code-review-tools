Pattern: Unused declaration

Issue: -

## Description

Declarations should be referenced at least once.

By default, detects unused `fileprivate`, `private` and `internal` declarations. Configure the rule with `include_public_and_open: true` to also detect unused `public` and `open` declarations.

Examples of **correct** code:
```swift
let kConstant = 0
_ = kConstant


struct Item {}
struct ResponseModel: Codable {
    let items: [Item]

    enum CodingKeys: String, CodingKey {
        case items = "ResponseItems"
    }
}

_ = ResponseModel(items: [Item()]).items


class ResponseModel {
    @objc func foo() {
    }
}
_ = ResponseModel()

```
Examples of **incorrect** code:
```swift

let ↓kConstant = 0


struct Item {}
struct ↓ResponseModel: Codable {
    let ↓items: [Item]

    enum ↓CodingKeys: String {
        case items = "ResponseItems"
    }
}


class ↓ResponseModel {
    func ↓foo() {
    }
}

```

## Further Reading

* [SwiftLint - Unused Declaration](https://github.com/realm/SwiftLint/blob/master/Rules.md#unused-declaration)