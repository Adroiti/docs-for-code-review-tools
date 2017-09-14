Pattern: Collection methods

Issue: -

## Description

This cop enforces the use of consistent method names
from the Enumerable module.

Unfortunately we cannot actually know if a method is from
Enumerable or not (static analysis limitation), so this cop
can yield some false positives.

## Default configuration

Attribute | Value
--- | ---
PreferredMethods | {"collect"=>"map", "collect!"=>"map!", "inject"=>"reduce", "detect"=>"find", "find_all"=>"select"}

## Further Reading

* [RuboCop - Style/CollectionMethods](https://rubocop.readthedocs.io/en/latest/cops_style/#stylecollectionmethods)
* [https://github.com/bbatsov/ruby-style-guide#map-find-select-reduce-size](https://github.com/bbatsov/ruby-style-guide#map-find-select-reduce-size)
