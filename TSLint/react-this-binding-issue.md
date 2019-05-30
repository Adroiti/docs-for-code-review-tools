Pattern: Problematic `this` binding

Issue: -

## Description

Several errors can occur when using `React` and `React.Component`
subclasses. When using React components you must be careful to correctly
bind the `this` reference on any methods that you pass off to child
components as callbacks.

For example, it is common to define a private method called `onClick` and then specify `onClick={this.onClick}` as a
JSX attribute. If you do this then the `this` reference will be
undefined when your private method is invoked. The React documentation
suggests that you bind the `this` reference on all of your methods
within the constructor: `this.onClick = this.onClick.bind(this);`. 

This rule will create a violation if:
-   a method reference is passed to a JSX attribute without being bound
    in the constructor
-   a method is bound multiple times in the constructor

Another issue that can occur is binding the `this` reference to a
function within the render() method. For example, many people will
create an anonymous lambda within the JSX attribute to avoid the `this`
binding issue: `onClick={() => { this.onClick(); }}`. The problem with
this is that a new instance of an anonymous function is created every
time render() is invoked. When React compares virtual DOM properties
within shouldComponentUpdate() then the onClick property will look like
a new property and force a re-render. You should avoid this pattern
because creating function instances within render methods breaks any
logic within shouldComponentUpdate() methods. 

This rule creates violations if:
-   an anonymous function is passed as a JSX attribute
-   if a function instantiated in local scope is passed as a JSX
    attribute
	
## Configuration

This rule can be configured via the `allow-anonymous-listeners` parameter. If you want to suppress violations for the anonymous listener scenarios then configure that rule like this:
```
"react-this-binding-issue": [true, {
    'allow-anonymous-listeners': true
}]
```

You can also pass in array of string which can act as bind method decorators:
```
"react-this-binding-issue": [true, {
    'bind-decorators': ['autobind']
}]
```

## Further Reading

* [TSLint - react-this-binding-issue](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)