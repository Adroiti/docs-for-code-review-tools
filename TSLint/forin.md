Pattern: Forin

Issue: -

## Description

Requires a `for ... in` statement to be filtered with an `if` statement.  
  
Rationale: 
    
    
    for (let key in someObject) {
        if (someObject.hasOwnProperty(key)) {
            // code here
        }
    }

## Further Reading

* [TSLint - forin](https://palantir.github.io/tslint/rules/forin)