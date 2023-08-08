Pattern: Use of `eval`

Issue: -

## Description

Never pass untrusted or user controlled input to `eval`.

Unless you are implementing a REPL like `irb` or `pry`, `eval` is almost certainly not what you want. Do not attempt to filter user input before passing it to `eval` - this approach is fraught with danger and will most likely open your application up to a serious remote code execution vulnerability.

## Examples

```ruby
# bad

eval(something)
binding.eval(something)
```

## Further Reading

* [Documentation for Ruby - eval](https://docs.ruby-lang.org/en/2.0.0/security_rdoc.html#label-eval)
* [RuboCop - Security/Eval](https://docs.rubocop.org/rubocop/cops_security.html#securityeval)
