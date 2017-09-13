Pattern: Style/TrivialAccessors

Issue: -

## Description

This cop looks for trivial reader/writer methods, that could
have been created with the attr_* family of functions automatically.

## Default configuration

Attribute | Value
--- | ---
ExactNameMatch | true
AllowPredicates | true
AllowDSLWriters | false
IgnoreClassMethods | false
Whitelist | to_ary, to_a, to_c, to_enum, to_h, to_hash, to_i, to_int, to_io, to_open, to_path, to_proc, to_r, to_regexp, to_str, to_s, to_sym

## Further Reading

* [RuboCop - Style/TrivialAccessors](https://rubocop.readthedocs.io/en/latest/cops_style/#styletrivialaccessors)
* [https://github.com/bbatsov/ruby-style-guide#attr_family](https://github.com/bbatsov/ruby-style-guide#attr_family)
