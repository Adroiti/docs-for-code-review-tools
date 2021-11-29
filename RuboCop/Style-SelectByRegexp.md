Pattern: Missing use of `grep`/`grep_v`

Issue: -

## Description

This rule looks for places where an subset of an Enumerable (array,
range, set, etc.; see note below) is calculated based on a `Regexp`
match, and suggests `grep` or `grep_v` instead.

NOTE: Hashes do not behave as you may expect with `grep`, which
means that `hash.grep` is not equivalent to `hash.select`. Although
RuboCop is limited by static analysis, this rule attempts to avoid
registering an offense when the receiver is a hash (hash literal,
`Hash.new`, `Hash#[]`, or `to_h`/`to_hash`).

NOTE: `grep` and `grep_v` were optimized when used without a block
in Ruby 3.0, but may be slower in previous versions.

### Safety

Auto-correction is marked as unsafe because `MatchData` will
not be created by `grep`, but may have previously been relied
upon after the `match?` or `=~` call.

Additionally, the rule cannot guarantee that the receiver of
`select` or `reject` is actually an array by static analysis,
so the correction may not be actually equivalent.

## Examples

```ruby
# bad (select or find_all)
array.select { |x| x.match? /regexp/ }
array.select { |x| /regexp/.match?(x) }
array.select { |x| x =~ /regexp/ }
array.select { |x| /regexp/ =~ x }

# bad (reject)
array.reject { |x| x.match? /regexp/ }
array.reject { |x| /regexp/.match?(x) }
array.reject { |x| x =~ /regexp/ }
array.reject { |x| /regexp/ =~ x }

# good
array.grep(regexp)
array.grep_v(regexp)
```

## Further Reading

* [RuboCop - Style/SelectByRegexp](https://docs.rubocop.org/rubocop/cops_style.html#styleselectbyregexp)
