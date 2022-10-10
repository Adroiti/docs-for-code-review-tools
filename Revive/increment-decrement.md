Pattern: Missing use of `++`/`--`

Issue: -

## Description

By convention, for better readability, incrementing an integer variable by 1 is recommended to be done using the `++` operator.
This rule spots expressions like `i += 1` and `i -= 1` and proposes to change them into `i++` and `i--`.

## Further Reading

* [Revive - increment-decrement](https://revive.run/r#increment-decrement)