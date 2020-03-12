Pattern: Missing use of `reduce(into:_:)`

Issue: -

## Description

Prefer `reduce(into:_:)` over `reduce(_:_:)` for copy-on-write types.

Examples of **correct** code:

```swift
let foo = values.reduce(into: "abc") { $0 += "\($1)" }


values.reduce(into: Array<Int>()) { result, value in
    result.append(value)
}


let rows = violations.enumerated().reduce(into: "") { rows, indexAndViolation in
    rows.append(generateSingleRow(for: indexAndViolation.1, at: indexAndViolation.0 + 1))
}


zip(group, group.dropFirst()).reduce(into: []) { result, pair in
    result.append(pair.0 + pair.1)
}


let foo = values.reduce(into: [String: Int]()) { result, value in
    result["\(value)"] = value
}


let foo = values.reduce(into: Dictionary<String, Int>.init()) { result, value in
    result["\(value)"] = value
}


let foo = values.reduce(into: [Int](repeating: 0, count: 10)) { result, value in
    result.append(value)
}


let foo = values.reduce(MyClass()) { result, value in
    result.handleValue(value)
    return result
}

```
Examples of **incorrect** code:

```swift

let bar = values.↓reduce("abc") { $0 + "\($1)" }


values.↓reduce(Array<Int>()) { result, value in
    result += [value]
}


let rows = violations.enumerated().↓reduce("") { rows, indexAndViolation in
    return rows + generateSingleRow(for: indexAndViolation.1, at: indexAndViolation.0 + 1)
}


zip(group, group.dropFirst()).↓reduce([]) { result, pair in
    result + [pair.0 + pair.1]
}


let foo = values.↓reduce([String: Int]()) { result, value in
    var result = result
    result["\(value)"] = value
    return result
}


let bar = values.↓reduce(Dictionary<String, Int>.init()) { result, value in
    var result = result
    result["\(value)"] = value
    return result
}


let bar = values.↓reduce([Int](repeating: 0, count: 10)) { result, value in
    return result + [value]
}

```

## Further Reading

* [SwiftLint - Reduce Into](https://realm.github.io/SwiftLint/reduce_into.html)