Pattern: Too many associated values in enum case

Issue: -

## Description

Number of associated values in an enum case should be low.

Examples of **correct** code:

```swift
enum Employee {
    case fullTime(name: String, retirement: Date, designation: String, contactNumber: Int)
    case partTime(name: String, age: Int, contractEndDate: Date)
}

enum Barcode {
    case upc(Int, Int, Int, Int)
}
```

Examples of **incorrect** code:

```swift
enum Employee {
    case ↓fullTime(name: String, retirement: Date, age: Int, designation: String, contactNumber: Int)
    case ↓partTime(name: String, contractEndDate: Date, age: Int, designation: String, contactNumber: Int)
}

enum Barcode {
    case ↓upc(Int, Int, Int, Int, Int, Int)
}
```

## Further Reading

* [SwiftLint - Enum Case Associated Values Count](https://realm.github.io/SwiftLint/enum_case_associated_values_count.html)