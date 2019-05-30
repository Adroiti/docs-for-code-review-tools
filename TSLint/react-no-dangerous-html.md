Pattern: Use of React's `dangerouslySetInnerHTML`

Issue: -

## Description

This rule finds usages of React's [dangerouslySetInnerHTML](https://facebook.github.io/react/tips/dangerously-set-inner-html.html). One should not use this API because it possible opens your system up to an XSS attack. 

## Suppressions

Suppressions can be specified in your tslint.json configuration file like this: 

```json
"react-no-dangerous-html": [true, 
    { 
        "file": "local/path/to/MyFile.ts", 
        "method": "render", 
        "comment": "Usage has been approved by our Security Group on 2015-03-12"
    }
]
```


## Further Reading

* [TSLint - react-no-dangerous-html](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)