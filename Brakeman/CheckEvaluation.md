Pattern: Evaluation of user input

Issue: -

## Description

User input in an `eval` statement is VERY dangerous, so this will always raise a warning. Brakeman looks for calls to `eval`, `instance_eval`, `class_eval`, and `module_eval`.

## Further Reading

* [Brakeman - Dangerous Evaluation](https://brakemanscanner.org/docs/warning_types/dangerous_eval/)