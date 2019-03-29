Pattern: Missing use of predicate matcher

Issue: -

## Description

Prefer using predicate matcher over using predicate method directly.

RSpec defines magic matchers for predicate methods. This rule recommends to use the predicate matcher instead of using predicate method directly.

## Examples

#### Strict: true, EnforcedStyle: inflected (default)

```ruby
# bad
expect(foo.something?).to be_truthy

# good
expect(foo).to be_something

# also good - It checks "true" strictly.
expect(foo).to be(true)
```
#### Strict: false, EnforcedStyle: inflected

```ruby
# bad
expect(foo.something?).to be_truthy
expect(foo).to be(true)

# good
expect(foo).to be_something
```
#### Strict: true, EnforcedStyle: explicit

```ruby
# bad
expect(foo).to be_something

# good - the above code is rewritten to it by this cop
expect(foo.something?).to be(true)
```
#### Strict: false, EnforcedStyle: explicit

```ruby
# bad
expect(foo).to be_something

# good - the above code is rewritten to it by this cop
expect(foo.something?).to be_truthy
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
Strict | `true` | Boolean
EnforcedStyle | `inflected` | `inflected`, `explicit`

## Further Reading

* [RSpec - RSpec/PredicateMatcher](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecpredicatematcher)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/PredicateMatcher](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/PredicateMatcher)
