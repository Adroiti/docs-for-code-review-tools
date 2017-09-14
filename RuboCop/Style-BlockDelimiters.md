Pattern: Block delimiters

Issue: -

## Description

Check for uses of braces or do/end around single line or
multi-line blocks.

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | line_count_based
SupportedStyles | line_count_based, semantic, braces_for_chaining
ProceduralMethods | benchmark, bm, bmbm, create, each_with_object, measure, new, realtime, tap, with_object
FunctionalMethods | let, let!, subject, watch
IgnoredMethods | lambda, proc, it

## Further Reading

* [RuboCop - Style/BlockDelimiters](https://rubocop.readthedocs.io/en/latest/cops_style/#styleblockdelimiters)
* [https://github.com/bbatsov/ruby-style-guide#single-line-blocks](https://github.com/bbatsov/ruby-style-guide#single-line-blocks)
