Pattern: Misused method from `Enumerable` module

Issue: -

## Description

This rule enforces the use of consistent method names from the `Enumerable` module.

Unfortunately this rule cannot actually know if a method is from `Enumerable` or not (static analysis limitation), so it can yield some false positives.

## Default configuration

Attribute | Value
--- | ---
PreferredMethods | {"collect"=>"map", "collect!"=>"map!", "inject"=>"reduce", "detect"=>"find", "find_all"=>"select"}

## Further Reading

* [RuboCop - Style/CollectionMethods](https://docs.rubocop.org/rubocop/cops_style.html#stylecollectionmethods)
* [https://github.com/bbatsov/ruby-style-guide#map-find-select-reduce-size](https://github.com/bbatsov/ruby-style-guide#map-find-select-reduce-size)
