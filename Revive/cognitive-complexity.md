Pattern: Cognitive complexity is too high

Issue: -

## Description

[Cognitive complexity](https://www.sonarsource.com/docs/CognitiveComplexity.pdf) is a measure of how hard code is to understand.
While cyclomatic complexity is good to measure "testability" of the code, cognitive complexity aims to provide a more precise measure of the difficulty of understanding the code.
Enforcing a maximum complexity per function helps to keep code readable and maintainable.

## Configuration

(int) the maximum function complexity

## Example:

```toml
[rule.cognitive-complexity]
  arguments =[7]
```

## Further Reading

* [Revive - cognitive-complexity](https://revive.run/r#cognitive-complexity)