Pattern: Missing Copyright

Issue: -

## Description

Checks that a copyright notice was given in each source file. The default can be changed as follows:

    Style/Copyright:
      Notice: '^Copyright (\(c\) )?2\d{3} Company Inc'

This regex string is treated as an unanchored regex.  For each file
that RuboCop scans, a comment that matches this regex must be found or
an offense is reported.

## Default configuration

Attribute | Value
--- | ---
Notice | ^Copyright (\(c\) )?2[0-9]{3} .+
AutocorrectNotice |

## Further Reading

* [RuboCop - Style/Copyright](https://rubocop.readthedocs.io/en/latest/cops_style/#stylecopyright)
