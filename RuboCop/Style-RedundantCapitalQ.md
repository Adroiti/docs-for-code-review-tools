Pattern: Unnecessary `%Q`

Issue: -

## Description

This rule checks for usage of the `%Q` syntax when when interpolation is not needed or `%q` would do.

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | lower_case_q
SupportedStyles | lower_case_q, upper_case_q

## Further Reading

* [RuboCop - Style/RedundantCapitalQ](https://rubocop.readthedocs.io/en/latest/cops_style/#styleredundantcapitalq)
