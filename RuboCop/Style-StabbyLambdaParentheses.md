Pattern: Style/StabbyLambdaParentheses

Issue: -

## Description

Check for parentheses around stabby lambda arguments.
There are two different styles. Defaults to `require_parentheses`.

### Example

```ruby
# require_parentheses - bad
->a,b,c { a + b + c }

# require_parentheses - good
->(a,b,c) { a + b + c}

# require_no_parentheses - bad
->(a,b,c) { a + b + c }

# require_no_parentheses - good
->a,b,c { a + b + c}
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | require_parentheses
SupportedStyles | require_parentheses, require_no_parentheses

## Further Reading

* [RuboCop - Style/StabbyLambdaParentheses](https://rubocop.readthedocs.io/en/latest/cops_style/#stylestabbylambdaparentheses)
* [https://github.com/bbatsov/ruby-style-guide#stabby-lambda-with-args](https://github.com/bbatsov/ruby-style-guide#stabby-lambda-with-args)
