Pattern: Inconsistent file name via regex

Issue: -

## Description

Enforce a certain file naming convention using a regular expression.

The convention can be configured using a regular expression (the default is `camelCase.js`). Additionally
exporting files can be ignored with a second configuration parameter.

```json
"filenames/match-regex": [2, "^[a-z_]+$", true]
```

With these configuration options, `camelCase.js` will be reported as an error while `snake_case.js` will pass.
Additionally the files that have a named default export (according to the logic in the `match-exported` rule) will be
ignored.  They could be linted with the `match-exported` rule.