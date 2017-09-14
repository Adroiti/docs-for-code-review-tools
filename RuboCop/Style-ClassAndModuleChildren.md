Pattern: Class and module children

Issue: -

## Description

This cop checks the style of children definitions at classes and
modules. Basically there are two different styles:

nested - have each child on its own line
  class Foo
    class Bar
    end
  end

compact - combine definitions as much as possible
  class Foo::Bar
  end

The compact style is only forced for classes/modules with one child.

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | nested
SupportedStyles | nested, compact

## Further Reading

* [RuboCop - Style/ClassAndModuleChildren](https://rubocop.readthedocs.io/en/latest/cops_style/#styleclassandmodulechildren)
* [https://github.com/bbatsov/ruby-style-guide#namespace-definition](https://github.com/bbatsov/ruby-style-guide#namespace-definition)
