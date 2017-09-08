Pattern: Unfiltered `for ... in`

Issue: -

## Description

Requires a `for ... in` statement to be filtered with an `if` statement.  
  
Rationale: 
    
    
    for (let key in someObject) {
        if (someObject.hasOwnProperty(key)) {
            // code here
        }
    }
	
This prevents accidental iteration over properties inherited from an object’s prototype.	

## Further Reading

* [TSLint - forin](https://palantir.github.io/tslint/rules/forin)
* [MDN web docs - for...in](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in)