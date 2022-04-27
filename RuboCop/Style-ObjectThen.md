Pattern: Missing use of `Object#yield_self`/`Object#then` name

Issue: -

## Description

This rule enforces the use of consistent method names
`Object#yield_self` or `Object#then`.

## Examples

#### EnforcedStyle: then (default)

```ruby
# bad
obj.yield_self { |x| x.do_something }

# good
obj.then { |x| x.do_something }
```

#### EnforcedStyle: yield_self

```ruby
# bad
obj.then { |x| x.do_something }

# good
obj.yield_self { |x| x.do_something }
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
EnforcedStyle | `then` | `then`, `yield_self`

## Further Reading

* [RuboCop - Style/ObjectThen](https://docs.rubocop.org/rubocop/cops_style.html#styleobjectthen)
* https://rubystyle.guide#object-yield-self-vs-object-then