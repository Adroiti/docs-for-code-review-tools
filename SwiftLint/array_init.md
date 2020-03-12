Pattern: Use of `seq.map { $0 }`

Issue: -

## Description

Prefer using `Array(seq)` over `seq.map { $0 }` to convert a sequence into an Array.

Examples of **correct** code:
```swift
Array(foo)


foo.map { $0.0 }


foo.map { $1 }


foo.map { $0() }


foo.map { ((), $0) }


foo.map { $0! }


foo.map { $0! /* force unwrap */ }


foo.something { RouteMapper.map($0) }

```
Examples of **incorrect** code:
```swift

↓foo.map({ $0 })


↓foo.map { $0 }


↓foo.map { return $0 }


↓foo.map { elem in
   elem
}


↓foo.map { elem in
   return elem
}


↓foo.map { (elem: String) in
   elem
}


↓foo.map { elem -> String in
   elem
}


↓foo.map { $0 /* a comment */ }

```

## Further Reading

* [SwiftLint - Array Init](https://realm.github.io/SwiftLint/array_init.html)