Pattern: Undocumented dynamic eval definition

Issue: -

## Description

When using `class_eval` (or other `eval`) with string interpolation, add a comment block showing its appearance if interpolated (a practice used in Rails code).

## Examples

```ruby
# from activesupport/lib/active_support/core_ext/string/output_safety.rb

# bad
UNSAFE_STRING_METHODS.each do |unsafe_method|
  if 'String'.respond_to?(unsafe_method)
    class_eval <<-EOT, __FILE__, __LINE__ + 1
      def #{unsafe_method}(*params, &block)
        to_str.#{unsafe_method}(*params, &block)
      end

      def #{unsafe_method}!(*params)
        @dirty = true
        super
      end
    EOT
  end
end

# good
UNSAFE_STRING_METHODS.each do |unsafe_method|
  if 'String'.respond_to?(unsafe_method)
    class_eval <<-EOT, __FILE__, __LINE__ + 1
      def #{unsafe_method}(*params, &block)       # def capitalize(*params, &block)
        to_str.#{unsafe_method}(*params, &block)  #   to_str.capitalize(*params, &block)
      end                                         # end

      def #{unsafe_method}!(*params)              # def capitalize!(*params)
        @dirty = true                             #   @dirty = true
        super                                     #   super
      end                                         # end
    EOT
  end
end
```

## Further Reading

* [RuboCop - Style/DocumentDynamicEvalDefinition](https://docs.rubocop.org/rubocop/cops_style.html#styledocumentdynamicevaldefinition)
