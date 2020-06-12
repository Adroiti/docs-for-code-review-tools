Pattern: Use of `has_and_belongs_to_many` instead of `has_many :through`

Issue: -

## Description

This rule checks for the use of the `has_and_belongs_to_many` macro. Using `has_many :through` allows additional attributes and validations on the join model.

## Default configuration

Attribute | Value
--- | ---
Include | app/models/\*\*/\*.rb

## Further Reading

* [RuboCop - Rails/HasAndBelongsToMany](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railshasandbelongstomany)
* [https://github.com/bbatsov/rails-style-guide#has-many-through](https://github.com/bbatsov/rails-style-guide#has-many-through)
