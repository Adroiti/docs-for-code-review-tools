Pattern: Use of `Range#include?` instead of `Range#cover?`

Issue: -

## Description

This rule identifies uses of `Range#include?`, which iterates over each
item in a `Range` to see if a specified item is there. In contrast,
`Range#cover?` simply compares the target item with the beginning and
end points of the `Range`. In a great majority of cases, this is what
is wanted.

Here is an example of a case where `Range#cover?` may not provide the
desired result:

    ('a'..'z').cover?('yellow') # => true

## Further Reading

* [RuboCop - Performance/RangeInclude](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performancerangeinclude)
* [https://github.com/JuanitoFatas/fast-ruby#cover-vs-include-code](https://github.com/JuanitoFatas/fast-ruby#cover-vs-include-code)
