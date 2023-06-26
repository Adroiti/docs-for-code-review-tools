Pattern: Invalid lambda parameter name

Issue: -

## Description

Checks that lambda parameter names conform to a format specified by the `format` property. 

## Examples

An example of how to configure the check is: 
    
```xml
<module name="LambdaParameterName"/>
```

An example of how to configure the check for names that begin with a lower case letter, followed by letters is: 
    
```xml
<module name="LambdaParameterName">
  <property name="format" value="^[a-z]([a-zA-Z]+)*$"/>
</module>
```

Example of checking with this config:
    
```java
public class TestClass {

	Function<String, String> function1 = str -> str.toUpperCase().trim();

	Function<String, String> function2 = _s -> _s.trim().toUpperCase(); // violation

	public boolean testMethod(String sentence) {
		return Stream.of(sentence.split(" "))
			.map(word -> word.trim())
			.anyMatch(Word -> "in".equals(Word)); // violation
	}

}
```

## Further Reading

* [checkstyle - LambdaParameterName](https://checkstyle.sourceforge.io/checks/naming/lambdaparametername.html#LambdaParameterName)