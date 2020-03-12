Pattern: Missing use of `isMultiple(of:)`

Issue: -

## Description

Prefer using the `isMultiple(of:)` function instead of using the remainder operator (`%`).

Examples of **correct** code:

```swift
cell.contentView.backgroundColor = indexPath.row.isMultiple(of: 2) ? .gray : .white


guard count.isMultiple(of: 2) else { throw DecodingError.dataCorrupted(...) }


sanityCheck(bytes > 0 && bytes.isMultiple(of: 4), "capacity must be multiple of 4 bytes")


guard let i = reversedNumbers.firstIndex(where: { $0.isMultiple(of: 2) }) else { return }


let constant = 56
let isMultiple = value.isMultiple(of: constant)


let constant = 56
let secret = value % constant == 5


let secretValue = (value % 3) + 2

```
Examples of **incorrect** code:

```swift

cell.contentView.backgroundColor = indexPath.row ↓% 2 == 0 ? .gray : .white


cell.contentView.backgroundColor = indexPath.row ↓% 2 != 0 ? .gray : .white


guard count ↓% 2 == 0 else { throw DecodingError.dataCorrupted(...) }


sanityCheck(bytes > 0 && bytes ↓% 4 == 0, "capacity must be multiple of 4 bytes")


guard let i = reversedNumbers.firstIndex(where: { $0 ↓% 2 == 0 }) else { return }


let constant = 56
let isMultiple = value ↓% constant == 0

```

## Further Reading

* [SwiftLint - Legacy Multiple](https://realm.github.io/SwiftLint/legacy_multiple.html)