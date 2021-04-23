Pattern: Use of `validates_format_of` with improper anchor

Issue: -

## Description

Reports any calls to `validates_format_of` which do not use `\A` and `\z` as anchors in the given regular expression.