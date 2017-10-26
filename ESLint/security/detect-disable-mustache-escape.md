Pattern: Use of `object.escapeMarkup = false`

Issue: -

## Description

Detects `object.escapeMarkup = false`, which can be used with some template engines to disable escaping of HTML entities. This can lead to Cross-Site Scripting (XSS) vulnerabilities.