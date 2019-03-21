Pattern: Use of restricted global

Issue: -

## Description

Disallow specific global variables.  
  
Rationale: 
    
    
    function broken(evt: Event) {
        // Meant to do something with `evt` but typed it incorrectly.
        Event.target;  // compiler error
        event.target;  // should be a lint failure
    }
    
Early Internet Explorer versions exposed the current DOM event as a global variable `event`, but using this variable has been considered a bad practice for a long time. Restricting this will make sure this variable isn’t used in browser code.

## Further Reading

* [TSLint - no-restricted-globals](https://palantir.github.io/tslint/rules/no-restricted-globals)