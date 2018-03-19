Pattern: File does not end with newline

Issue: -

## Description

This rule enforces a new line character (`\n`) at the end of files.

The POSIX standard [requires the last line to end with a new line character](http://pubs.opengroup.org/onlinepubs/9699919799/basedefs/V1_chap03.html#tag_03_206). All UNIX tools expect a new line at the end of files. Most text editors use this convention too.

## Further Reading

* [Yamllint - new_line_at_end_of_file](https://yamllint.readthedocs.io/en/stable/rules.html#module-yamllint.rules.new_line_at_end_of_file)