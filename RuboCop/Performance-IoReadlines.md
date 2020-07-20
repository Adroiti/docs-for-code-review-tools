Pattern: Missing use of `each_line`

Issue: -

## Description

Identifies places where inefficient `readlines` method can be replaced by `each_line` to avoid fully loading file content into memory.

## Examples

```ruby
# bad
File.readlines('testfile').each { |l| puts l }
IO.readlines('testfile', chomp: true).each { |l| puts l }

conn.readlines(10).map { |l| l.size }
file.readlines.find { |l| l.start_with?('#') }
file.readlines.each { |l| puts l }

# good
File.open('testfile', 'r').each_line { |l| puts l }
IO.open('testfile').each_line(chomp: true) { |l| puts l }

conn.each_line(10).map { |l| l.size }
file.each_line.find { |l| l.start_with?('#') }
file.each_line { |l| puts l }
```

## Further Reading

* [RuboCop - Performance/IoReadlines](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performanceioreadlines)