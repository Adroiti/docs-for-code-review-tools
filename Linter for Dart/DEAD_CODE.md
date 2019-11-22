Pattern: Unreachable code

Issue: -

## Description

Unreachable code can never be executed because there exists no control flow path to the code from the rest of the program. It is generally considered undesirable for a number of reasons, including increased code size and increased time and effort for maintenance. Consider deleting unused code to resolve this issue.

Example of **incorrect** code:

```go
void f(int x) {
  return;
  print('debug: $x');
}
```

Example of **correct** code:

```go
void f(int x) {
  print('debug: $x');
}
```

## Further Reading

* [SourceMaking - Dead Code](https://sourcemaking.com/refactoring/smells/dead-code)
