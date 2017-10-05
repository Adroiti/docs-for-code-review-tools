Pattern: Invalid closure parameter position

Issue: -

## Description

Closure parameters should be on the same line as opening brace.

Examples of **correct** code:
```swift
[1, 2].map { $0 + 1 }


[1, 2].map({ $0 + 1 })


[1, 2].map { number in
 number + 1 
}


[1, 2].map { number -> Int in
 number + 1 
}


[1, 2].map { (number: Int) -> Int in
 number + 1 
}


[1, 2].map { [weak self] number in
 number + 1 
}


[1, 2].something(closure: { number in
 number + 1 
})


let isEmpty = [1, 2].isEmpty()


rlmConfiguration.migrationBlock.map { rlmMigration in
return { migration, schemaVersion in
rlmMigration(migration.rlmMigration, schemaVersion)
}
}


let mediaView: UIView = { [weak self] index in
   return UIView()
}(index)

```
Examples of **incorrect** code:
```swift

[1, 2].map {
 ↓number in
 number + 1 
}


[1, 2].map {
 ↓number -> Int in
 number + 1 
}


[1, 2].map {
 (↓number: Int) -> Int in
 number + 1 
}


[1, 2].map {
 [weak self] ↓number in
 number + 1 
}


[1, 2].map { [weak self]
 ↓number in
 number + 1 
}


[1, 2].map({
 ↓number in
 number + 1 
})


[1, 2].something(closure: {
 ↓number in
 number + 1 
})


[1, 2].reduce(0) {
 ↓sum, ↓number in
 number + sum 
}

```

## Further Reading

* [SwiftLint - Closure Parameter Position](https://github.com/realm/SwiftLint/blob/master/Rules.md#closure-parameter-position)