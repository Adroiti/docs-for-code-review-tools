Pattern: Malformed curly spacing for JSX attribute

Issue: -

## Description

Consistently use spaces around the brace characters of JSX attributes.
You can either allow or ban spaces between the braces and the values
they enclose.  
One of the two following options are required:
-   `"always"` enforces a space inside of curly braces (default)
-   `"never"` disallows spaces inside of curly braces

## Configuration

By default, braces spanning multiple lines are not allowed with either setting. If you want to allow them you can specify an additional `allowMultiline` property with the value false.  

Examples:
-   `"react-tsx-curly-spacing": [true, "always"]`
-   `"react-tsx-curly-spacing": [true, "never"]`
-   `"react-tsx-curly-spacing": [true, "never", {"allowMultiline": false}]`

## Further Reading

* [TSLint - react-tsx-curly-spacing](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)