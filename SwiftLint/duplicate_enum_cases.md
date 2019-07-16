Pattern: Duplicate `enum` case

Issue: -

## Description

Enum can't contain multiple cases with the same name.

Examples of **correct** code:

```swift
enum PictureImport {
    case addImage(image: UIImage)
    case addData(data: Data)
}


enum A {
    case add(image: UIImage)
}
enum B {
    case add(image: UIImage)
}

```
Examples of **incorrect** code:
```swift

enum PictureImport {
    case ↓add(image: UIImage)
    case addURL(url: URL)
    case ↓add(data: Data)
}

```

## Further Reading

* [SwiftLint - Duplicate Enum Cases](https://github.com/realm/SwiftLint/blob/master/Rules.md#duplicate-enum-cases)