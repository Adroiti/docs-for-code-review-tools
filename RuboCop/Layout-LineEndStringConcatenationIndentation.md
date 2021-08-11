Pattern: Malformed end-line indentation 

Issue: -

## Description

Checks the indentation of the next line after a line that ends with a string
literal and a backslash.

If `EnforcedStyle: aligned` is set, the concatenated string parts shall be aligned with the
first part. There are some exceptions, such as implicit return values, where the
concatenated string parts shall be indented regardless of `EnforcedStyle` configuration.

If `EnforcedStyle: indented` is set, it's the second line that shall be indented one step
more than the first line. Lines 3 and forward shall be aligned with line 2. Here too there
are exceptions. Values in a hash literal are always aligned.

## Examples

```ruby
# bad
def some_method
  'x' \
  'y' \
  'z'
end

my_hash = {
  first: 'a message' \
    'in two parts'
}

# good
def some_method
  'x' \
    'y' \
    'z'
end

my_hash = {
  first: 'a message' \
         'in two parts'
}
```

## Further Reading

* [RuboCop - Layout/LineEndStringConcatenationIndentation](https://docs.rubocop.org/rubocop/cops_layout.html#layoutlineendstringconcatenationindentation)
