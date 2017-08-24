Pattern: Malformed Javadoc comment for method or constructor

Issue: -

## Description

Checks the Javadoc of a method or constructor. By default, does not check for unused throws. To allow documented `java.lang.RuntimeException`s that are not declared, set property `allowUndeclaredRTE` to true. The scope to verify is specified using the `Scope` class and defaults to `Scope.PRIVATE`. To verify another scope, set property scope to a different [scope](http://checkstyle.sourceforge.net/property_types.html#scope). 

Error messages about parameters and type parameters for which no param tags are present can be suppressed by defining property `allowMissingParamTags`. Error messages about exceptions which are declared to be thrown, but for which no throws tag is present can be suppressed by defining property `allowMissingThrowsTags`. Error messages about methods which return non-void but for which no return tag is present can be suppressed by defining property `allowMissingReturnTag`. 

Javadoc is not required on a method that is tagged with the `@Override` annotation. However under Java 5 it is not possible to mark a method required for an interface (this was _corrected_ under Java 6). Hence Checkstyle supports using the convention of using a single `{@inheritDoc}` tag instead of all the other tags. 

Note that only inheritable items will allow the `{@inheritDoc}` tag to be used in place of comments. Static methods at all visibilities, private non-static methods and constructors are not inheritable. 

For example, if the following method is implementing a method required by an interface, then the Javadoc could be done as: 


```java
/** {@inheritDoc} */
public int checkReturnTag(final int aTagIndex,
             JavadocTag[] aTags,
             int aLineNo)
```

The classpath may need to be configured to locate the class information. The classpath configuration is dependent on the mechanism used to invoke Checkstyle. 

## Examples

To configure the default check: 


```xml
<module name="JavadocMethod"/>
```
        

To configure the check for `public` scope and to allow documentation of undeclared RuntimeExceptions: 


```xml
<module name="JavadocMethod">
   <property name="scope" value="public"/>
   <property name="allowUndeclaredRTE" value="true"/>
</module>
```
        

To configure the check for for `public` scope, to allow documentation of undeclared RuntimeExceptions, while ignoring any missing param tags is: 


```xml
<module name="JavadocMethod">
  <property name="scope" value="public"/>
  <property name="allowUndeclaredRTE" value="true"/>
  <property name="allowMissingParamTags" value="true"/>
</module>
```
        

To configure the check for methods which are in `private` , but not in `protected` scope: 


```xml
<module name="JavadocMethod">
   <property name="scope" value="private"/>
   <property name="excludeScope" value="protected"/>
</module>
```
        

To configure the check for ignoring methods named `foo(),foo1(),foo2()`, etc.: 


```xml
<module name="JavadocMethod">
   <property name="ignoreMethodNamesRegex" value="^foo.*$"/>
</module>
```

## Further Reading

* [checkstyle - JavadocMethod](http://checkstyle.sourceforge.net/config_javadoc.html#JavadocMethod)
