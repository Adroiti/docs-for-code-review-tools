Pattern: Missing use of `where` clause

Issue: -

## Description

`where` clauses are preferred over a single `if` inside a `for`.

Examples of **correct** code:
```swift
for user in users where user.id == 1 { }


for user in users {
   if let id = user.id { }
}


for user in users {
   if var id = user.id { }
}


for user in users {
   if user.id == 1 { } else { }
}


for user in users {
   if user.id == 1 {
} else if user.id == 2 { }
}


for user in users {
   if user.id == 1 { }
   print(user)
}


for user in users {
   let id = user.id
   if id == 1 { }
}


for user in users {
   if user.id == 1 { }
   return true
}


for user in users {
   if user.id == 1 && user.age > 18 { }
}

```
Examples of **incorrect** code:
```swift

for user in users {
   ↓if user.id == 1 { return true }
}

```

## Further Reading

* [SwiftLint - For Where](https://realm.github.io/SwiftLint/for_where.html)