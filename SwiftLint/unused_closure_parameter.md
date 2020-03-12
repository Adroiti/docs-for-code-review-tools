Pattern: Unused closure parameter

Issue: -

## Description

Unused parameter in a closure should be replaced with `_`.

Examples of **correct** code:
```swift
[1, 2].map { $0 + 1 }


[1, 2].map({ $0 + 1 })


[1, 2].map { number in
 number + 1 
}


[1, 2].map { _ in
 3 
}


[1, 2].something { number, idx in
 return number * idx
}


let isEmpty = [1, 2].isEmpty()


violations.sorted(by: { lhs, rhs in 
 return lhs.location > rhs.location
})


rlmConfiguration.migrationBlock.map { rlmMigration in
return { migration, schemaVersion in
rlmMigration(migration.rlmMigration, schemaVersion)
}
}


genericsFunc { (a: Type, b) in
a + b
}


var label: UILabel = { (lbl: UILabel) -> UILabel in
   lbl.backgroundColor = .red
   return lbl
}(UILabel())


hoge(arg: num) { num in
  return num
}

```
Examples of **incorrect** code:
```swift

[1, 2].map { ↓number in
 return 3
}


[1, 2].map { ↓number in
 return numberWithSuffix
}


[1, 2].map { ↓number in
 return 3 // number
}


[1, 2].map { ↓number in
 return 3 "number"
}


[1, 2].something { number, ↓idx in
 return number
}


genericsFunc { (↓number: TypeA, idx: TypeB) in return idx
}


hoge(arg: num) { ↓num in
}


fooFunc { ↓아 in
 }

```

## Further Reading

* [SwiftLint - Unused Closure Parameter](https://realm.github.io/SwiftLint/unused_closure_parameter.html)