Pattern: Missing use of `attr { CONST }`

Issue: -

## Description

Enforces `attr { CONST }` instead of `attr CONST` in factories, because the latter forces autoload, which slows down spec startup time and Zeus reload time after touching a model.

## Further Reading

* [RuboCop - Airbnb/FactoryAttrReferencesClass](https://github.com/airbnb/ruby/blob/master/rubocop-airbnb/lib/rubocop/cop/airbnb/factory_attr_references_class.rb)
