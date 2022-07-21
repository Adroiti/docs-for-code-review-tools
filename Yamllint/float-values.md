Pattern: Forbidden value for floating-point number

Issue: -

## Description

Use this rule to limit the permitted values for floating-point numbers. YAML permits three classes of float expressions: approximation to real numbers, positive and negative infinity and “not a number”.

### Options

- Use require-numeral-before-decimal to require floats to start with a numeral (ex `0.0` instead of `.0`).
- Use forbid-scientific-notation to forbid scientific notation.
- Use forbid-nan to forbid NaN (not a number) values.
- Use forbid-inf to forbid infinite values.

### Default values (when enabled)

```yaml
rules:
  float-values:
    forbid-inf: false
    forbid-nan: false
    forbid-scientific-notation: false
    require-numeral-before-decimal: false
```

## Further Reading

* [Yamllint - float-values](https://yamllint.readthedocs.io/en/stable/rules.html#module-yamllint.rules.float_values)