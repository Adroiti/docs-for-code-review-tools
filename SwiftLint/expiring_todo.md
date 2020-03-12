Pattern: Unresolved expired warning comment 

Issue: -

## Description

TODOs and FIXMEs should be resolved prior to their expiry date.

Examples of **correct** code:

```swift
// notaTODO:

// notaFIXME:

// TODO: [12/31/9999]

// TODO(note)

// FIXME(note)

/* FIXME: */
```
Examples of **incorrect** code:

```swift
// TODO: [10/14/2019]

// FIXME: [10/14/2019]
```

## Further Reading

* [SwiftLint - ExpiringTodo](https://realm.github.io/SwiftLint/expiring_todo.html)