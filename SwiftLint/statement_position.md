Pattern: Malformed statement position

Issue: -

## Description

`else` and `catch` should be on the same line, one space after the previous declaration.

Examples of **correct** code:
```swift
} else if {


} else {


} catch {


"}else{"


struct A { let catchphrase: Int }
let a = A(
 catchphrase: 0
)


struct A { let `catch`: Int }
let a = A(
 `catch`: 0
)

```
Examples of **incorrect** code:
```swift

↓}else if {


↓}  else {


↓}
catch {


↓}
	  catch {

```

## Further Reading

* [SwiftLint - Statement Position](https://github.com/realm/SwiftLint/blob/master/Rules.md#statement-position)