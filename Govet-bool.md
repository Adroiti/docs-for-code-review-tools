Pattern: Mistakes involving boolean operators

Issue: -

## Description

This rule checks for boolean evaluations that are redundant, suspect or having side effects. 

_Redundant_ code may increase maintenance costs by making code more difficult to change and to understand. Remove such code to resolve this issue.

_Suspect_ expressions could mean that evaluation is always true or always false resulting in redundant or unreachable code. 

_Side effects_ may alter remaining condition and introduce subtle and hard to detect bugs. Consider moving such code out of boolean expression.


Example of **incorrect** code:

```go
_ = f == nil || f == nil // redundant or: f == nil
```

Example of **correct** code:

```go
_ = f == nil
```

## Further Reading

* [Go - Boolean types](https://golang.org/ref/spec#Boolean_types)
* [Go Vet - bool](https://golang.org/cmd/vet/#hdr-Boolean_conditions)
