Pattern: Use of instance variables in helper

Issue: -

## Description

Relying on instance variables makes it difficult to re-use helper methods.

If it seems awkward to explicitly pass in each dependent variable, consider moving the behavior elsewhere, for example to a model, decorator or presenter.

## Default configuration

Attribute | Value
--- | ---
Include | `app/helpers/**/*.rb`

## Further Reading

* [RuboCop - Rails/HelperInstanceVariable](https://docs.rubocop.org/rubocop-rails/cops_rails.html)
