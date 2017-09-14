Pattern: Malformed bare percent literal

Issue: -

## Description

This cop checks if usage of `%()` or `%Q` matches configuration.


## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | bare_percent
SupportedStyles | percent_q, bare_percent

## Further Reading

* [RuboCop - Style/BarePercentLiterals](https://rubocop.readthedocs.io/en/latest/cops_style/#stylebarepercentliterals)
* [https://github.com/bbatsov/ruby-style-guide#percent-q-shorthand](https://github.com/bbatsov/ruby-style-guide#percent-q-shorthand)
