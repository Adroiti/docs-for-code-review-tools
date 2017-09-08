Pattern: Malformed curly braces

Issue: -

## Description

Enforces braces for `if`/`for`/`do`/`while` statements.  
  
Rationale: 
    
    
    if (foo === bar)
        foo++;
        bar++;
		
		
In the code above, the author almost certainly meant for both `foo++` and `bar++` to be executed only if `foo === bar`. However, he forgot braces and `bar++` will be executed no matter what. This rule could prevent such a mistake.		

## Further Reading

* [TSLint - curly](https://palantir.github.io/tslint/rules/curly)