Pattern: Redundant `%q` or `%Q`

Issue: -

## Description

This rule checks for usage of the `%q`/`%Q` syntax when `''` or `""` would do. Regular string literals are more readable and should be preferred unless a lot of characters would have to be escaped in them.

## Examples

```ruby
# bad
name = %q(Bruce Wayne)
time = %q(8 o'clock)
question = %q("What did you say?")

# good
name = 'Bruce Wayne'
time = "8 o'clock"
question = '"What did you say?"'
quote = %q(<p class='quote'>"What did you say?"</p>)
```

## Further Reading

* [RuboCop - Style/RedundantPercentQ](https://docs.rubocop.org/rubocop/cops_style.html#styleredundantpercentq)
* [https://github.com/bbatsov/ruby-style-guide#percent-q](https://github.com/bbatsov/ruby-style-guide#percent-q)
