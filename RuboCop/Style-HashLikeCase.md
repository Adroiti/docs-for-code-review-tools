Pattern: Use of `case-when` instead of hash lookup

Issue: -

## Description

Checks for places where `case-when` represents a simple 1:1 mapping and can be replaced with a hash lookup.

## Examples

```ruby
# bad
case country
when 'europe'
  'http://eu.example.com'
when 'america'
  'http://us.example.com'
when 'australia'
  'http://au.example.com'
end

# good
SITES = {
  'europe'    => 'http://eu.example.com',
  'america'   => 'http://us.example.com',
  'australia' => 'http://au.example.com'
}
SITES[country]
```

## Further Reading

* [RuboCop - Style/HashLikeCase](https://docs.rubocop.org/rubocop/cops_style.html#stylehashlikecase)
