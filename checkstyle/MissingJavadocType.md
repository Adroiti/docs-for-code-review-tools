Pattern: Missing Javadoc comment

Issue: -

## Description

Checks for missing Javadoc comments for class, enum, interface, and annotation interface definitions. The scope to verify is specified using the `Scope` class and defaults to `Scope.PUBLIC`. To verify another scope, set property scope to one of the `Scope` constants. 

## Examples

To configure the default check to make sure all public class, enum, interface, and annotation interface, definitions have javadocs: 
    

    <module name="MissingJavadocType"/>

            

Example:
    

    public class PublicClass {} // violation

    private class PublicClass {}

    protected class PublicClass {}

    class PackagePrivateClass {}

            

To configure the check for `private` scope: 
    

    <module name="MissingJavadocType">

      <property name="scope" value="private"/>

    </module>


Example:
    

    public class PublicClass {} // violation

    private class PublicClass {} // violation

    protected class PublicClass {} // violation

    class PackagePrivateClass {} // violation

            

To configure the check for `private` classes only: 
    

    <module name="MissingJavadocType">

      <property name="scope" value="private"/>

      <property name="excludeScope" value="package"/>

    </module>

            

Example:
    

    public class PublicClass {}

    private class PublicClass {} // violation

    protected class PublicClass {}

    class PackagePrivateClass {}

            

Example that allows missing comments for classes annotated with `@SpringBootApplication` and `@Configuration`: 
    

    @SpringBootApplication // no violations about missing comment on class

    public class Application {}

    

    @Configuration // no violations about missing comment on class

    class DatabaseConfiguration {}

            

Use following configuration:
       

    <module name="MissingJavadocType">

      <property name="skipAnnotations" value="SpringBootApplication,Configuration"/>

    </module>


## Further Reading

* [checkstyle - MissingJavadocType](http://checkstyle.sourceforge.net/config_javadoc.html)