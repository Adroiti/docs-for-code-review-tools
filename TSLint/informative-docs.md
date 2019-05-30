Pattern: Uninformative comment

Issue: -

## Description

Enforces that comments do more than just reiterate names of objects.
Either be informative with comments or don't include a comment. You can
override the default list of "useless" words ignored by the comment
checker:
```
"informative-docs": [true, {
    "useless-words": ["a", "an", "the", "text"]
}]
```

You can indicate words as synonyms (aliases) of each other:
```
"informative-docs": [true, {
        "aliases": {
            text: ["emoji", "smiley"]
        }]
```

## Further Reading

* [TSLint - informative-docs](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)