Pattern: Use of `;` for empty loop

Issue: -

## Description

Empty loop bodies should use `{}` or `continue`, but not a single semicolon.

Example of **incorrect** code:

```cpp
while (condition) {
  // Repeat test until it returns false.
}
for (int i = 0; i < kSomeNumber; ++i) {}  // Good - one newline is also OK.
while (condition) continue;  // Good - continue indicates no logic.
```

Example of **correct** code:

```python
while (condition);  // Bad - looks like part of do/while loop.
```

## Further Reading

* [Google C++ Style Guide - Loops and Switch Statements](https://google.github.io/styleguide/cppguide.html#Loops_and_Switch_Statements)
