Pattern: Inconsistent global variable name

Issue: -

## Description

This cop enforces naming for global variables. By default, it recommends to avoid using Perl-style special variables (like `$:`, `$;`, etc. ). They are quite cryptic and their use in anything but one-liner scripts is discouraged. Use the human-friendly aliases provided by the `English` library.

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | use_english_names
SupportedStyles | use_perl_names, use_english_names

## Further Reading

* [RuboCop - Style/SpecialGlobalVars](https://rubocop.readthedocs.io/en/latest/cops_style/#stylespecialglobalvars)
* [https://github.com/bbatsov/ruby-style-guide#no-cryptic-perlisms](https://github.com/bbatsov/ruby-style-guide#no-cryptic-perlisms)
