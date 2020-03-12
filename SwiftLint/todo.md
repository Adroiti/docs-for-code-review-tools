Pattern: Unresolved warning comment

Issue: -

## Description

Developers often add comments to code which is not complete or needs review. Most likely you want to fix or review the code, and then remove the comment, before you consider the code to be production ready.

Examples of **correct** code:
```swift
// notaTODO:


// notaFIXME:

```
Examples of **incorrect** code:
```swift

// ↓TODO:


// ↓FIXME:


// ↓TODO(note)


// ↓FIXME(note)


/* ↓FIXME: */


/* ↓TODO: */


/** ↓FIXME: */


/** ↓TODO: */

```

## Further Reading

* [SwiftLint - Todo](https://realm.github.io/SwiftLint/todo.html)