Pattern: HTML XSS vulnerability

Issue: -

## Description

This rule aims to catch as many XSS issues by examining the code. It checks for mixed html/non-html content, unescaped input, etc.

The following patterns are considered warnings:

```js

// Mixed content
var x = '<div>' + input + '</div>';
$node.html( '<div>' + input + '</div>' );

// Unsafe container names.
var html = input;
var text = htmlInput;
displayValue( htmlInput );

// Checking certain expression parameters that might end up in the variables.
var htmlItems = [ input1, input2 ].join();
var textItems = [ '<div>', input, '</div>' ].join();
var tag = isNumbered ? '<ol>' : '<ul>';

// Checking function return values.
var createHtml = function( item ) { return item.name; }
var createBox = function( item ) { return '<div>' + encode( item ) + '</div>' }

```

The following patterns are not warnings:

```js

// Proper encoding
var html = '<div>' + encode( input ) + '</div>';
$node.html( '<div>' + encode( input ) + '</div>' );

// Proper container names
var html = '<img src="happy.png">';
var text = textbox.value;

```

### Options

```js
"xss/no-mixed-html": [ 2, {
    "htmlVariableRules": [ "AsHtml", "HtmlEncoded/i", "^html$" ],
    "htmlFunctionRules": [ ".asHtml/i", "toHtml" ],
    "functions": {
        "$": {
            "htmlInput": true,
            "safe": [ "document", "this" ]
        },
        ".html": {
            "htmlInput": true,
            "htmlOutput": true
        },
        ".join": {
            "passthrough": { "obj": true, "args": true }
        }
    }
} ];
```

#### `htmlVariableRules`, `htmlFunctionRules`

`htmlVariableRules` and `htmlFunctionRules` specify the naming convention used
for storing HTML variables and defining functions returning HTML values. Both
of these options are defined as Regex-arrays. The regex options, such as case
insensitive matching can be defined with a delimiting '/'.


## When Not To Use It

If you are creating a Node.js application that doesn't output any HTML, you can
safely disable this rule.

## Further Reading

- [XSS Prevention Cheat Sheet - OWASP](https://www.owasp.org/index.php/XSS_%28Cross_Site_Scripting%29_Prevention_Cheat_Sheet)
