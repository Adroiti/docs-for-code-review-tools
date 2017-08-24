Pattern: Wrong visibility for class member

Issue: -

## Description

Checks visibility of class members. Only static final, immutable or annotated by specified annotation members may be public; other class members must be private unless the property `protectedAllowed` or `packageAllowed` is set. 

Public members are not flagged if the name matches the public member regular expression (contains `"^serialVersionUID$"` by default). 

Note that Checkstyle 2 used to include `"^f[A-Z][a-zA-Z0-9]*$"` in the default pattern to allow names used in container-managed persistence for Enterprise JavaBeans (EJB) 1.1 with the default settings. With EJB 2.0 it is no longer necessary to have public access for persistent fields, so the default has been changed. 

Rationale: Enforce encapsulation. 

Check also has options making it less strict: 

**ignoreAnnotationCanonicalNames** \- the list of annotations which ignore variables in consideration. If user will provide short annotation name that type will match to any named the same type without consideration of package 

**allowPublicFinalFields** \- which allows public final fields. Default value is **false**

**allowPublicImmutableFields** \- which allows immutable fields to be declared as public if defined in final class. Default value is **false**

Field is known to be immutable if: \- It's declared as final \- Has either a primitive type or instance of class user defined to be immutable (such as String, ImmutableCollection from Guava and etc) 

Classes known to be immutable are listed in **immutableClassCanonicalNames** by their **canonical** names. 

Rationale: Forcing all fields of class to have private modified by default is good in most cases, but in some cases it drawbacks in too much boilerplate get/set code. One of such cases are immutable classes. 

**Restriction**: check doesn't check if class is immutable, there's no checking if accessory methods are missing and all fields are immutable, we only check **if current field is immutable or final**. Under the flag **allowPublicImmutableFields**, the enclosing class must also be final, to encourage immutability. Under the flag **allowPublicFinalFields**, the final modifier on the enclosing class is optional. 

Star imports are out of scope of this Check. So if one of type imported via **star import** collides with user specified one by its short name - there won't be Check's violation. 

## Examples

To configure the check: 


```xml
<module name="VisibilityModifier"/>
```
        

To configure the check so that it allows package visible members: 


```xml
<module name="VisibilityModifier">
    <property name="packageAllowed" value="true"/>
</module>
```
        

To configure the check so that it allows no public members: 


```xml
<module name="VisibilityModifier">
    <property name="publicMemberPattern" value="^$"/>
</module>
```
        

To configure the check so that it allows public immutable fields (mostly for immutable classes): 


```xml
<module name="VisibilityModifier">
    <property name="allowPublicImmutableFields" value="true"/>
 </module>
```
        

Example of allowed public immutable fields: 


```java
public class ImmutableClass
{
    public final ImmutableSet<String> includes; // No warning
    public final ImmutableSet<String> excludes; // No warning
    public final java.lang.String notes; // No warning
    public final BigDecimal value; // No warning
 

    public ImmutableClass(Collection<String> includes, Collection<String> excludes,
    BigDecimal value, String notes)
    {
        this.includes = ImmutableSet.copyOf(includes);
        this.excludes = ImmutableSet.copyOf(excludes);
        this.value = value;
        this.notes = notes;
    }
}
```
        

To configure the check in order to allow user specified immutable class names: 


```xml
<module name="VisibilityModifier">
    <property name="allowPublicImmutableFields" value="true"/>
    <property name="immutableClassCanonicalNames" value="
    com.google.common.collect.ImmutableSet"/>
</module>
```
        

Example of allowed public immutable fields: 


```java
public class ImmutableClass
{
    public final ImmutableSet<String> includes; // No warning
    public final ImmutableSet<String> excludes; // No warning
    public final java.lang.String notes; // Warning here because
                            //'java.lang.String' wasn't specified as allowed class
    public final int someValue; // No warning
 

    public ImmutableClass(Collection<String> includes, Collection<String> excludes,
    String notes, int someValue)
    {
        this.includes = ImmutableSet.copyOf(includes);
        this.excludes = ImmutableSet.copyOf(excludes);
        this.value = value;
        this.notes = notes;
        this.someValue = someValue;
    }
}
```
        

Note, if allowPublicImmutableFields is set to true, the check will also check whether generic type parameters are immutable. If at least one generic type parameter is mutable, there will be a violation. 


```xml
<module name="VisibilityModifier">
  <property name="allowPublicImmutableFields" value="true"/>
  <property name="immutableClassCanonicalNames" value="
  com.google.common.collect.ImmutableSet, com.google.common.collect.ImmutableMap,java.lang.String"/>
</module>
```
        

Example of how the check works: 


```java
public final class Test {
    public final String s;
    public final ImmutableSet<String> names;
    public final ImmutableSet<Object> objects; // violation (Object class is mutable)
    public final ImmutableMap<String, Object> links; // violation (Object class is mutable)
 

    public Test() {
        s = "Hello!";
        names = ImmutableSet.of();
        objects = ImmutableSet.of();
        links = ImmutableMap.of();
    }
}
```
        

To configure the check passing fields annotated with `@com.annotation.CustomAnnotation`: 


```xml
<module name="VisibilityModifier">
  <property name="ignoreAnnotationCanonicalNames" value=
  "com.annotation.CustomAnnotation"/>
</module>
```
        

Example of allowed field: 


```java
class SomeClass
{
    @com.annotation.CustomAnnotation
    String annotatedString; // no warning
    @CustomAnnotation
    String shortCustomAnnotated; // no warning
}
```
        

To configure the check passing fields annotated with `@org.junit.Rule`, `@org.junit.ClassRule` and `@com.google.common.annotations.VisibleForTesting` annotations: 


```xml
<module name="VisibilityModifier"/>
```
        

Example of allowed fields: 


```java
class SomeClass
{
    @org.junit.Rule
    public TemporaryFolder publicJUnitRule = new TemporaryFolder(); // no warning
    @org.junit.ClassRule
    public static TemporaryFolder publicJUnitClassRule = new TemporaryFolder(); // no warning
    @com.google.common.annotations.VisibleForTesting
    public String testString = ""; // no warning
}
```
        

To configure the check passing fields annotated with short annotation name: 


```xml
<module name="VisibilityModifier">
  <property name="ignoreAnnotationCanonicalNames"
  value="CustomAnnotation"/>
</module>
```
        

Example of allowed fields: 


```java
class SomeClass
{
    @CustomAnnotation
    String customAnnotated; // no warning
    @com.annotation.CustomAnnotation
    String customAnnotated1; // no warning
    @mypackage.annotation.CustomAnnotation
    String customAnnotatedAnotherPackage; // another package but short name matches
                             // so no violation
}
```
        

To understand the difference between allowPublicImmutableFields and allowPublicFinalFields options, please, study the following examples. 

1) To configure the check to use only 'allowPublicImmutableFields' option: 


```xml
<module name="VisibilityModifier">
  <property name="allowPublicImmutableFields" value="true"/>
</module>
```
        

Code example: 


```java
public class InputPublicImmutable {
  public final int someIntValue; // violation
  public final ImmutableSet<String> includes; // violation
  public final java.lang.String notes; // violation
  public final BigDecimal value; // violation
  public final List list; // violation
 

  public InputPublicImmutable(Collection<String> includes,
        BigDecimal value, String notes, int someValue, List l) {
    this.includes = ImmutableSet.copyOf(includes);
    this.value = value;
    this.notes = notes;
    this.someIntValue = someValue;
    this.list = l;
  }
}
```
        

2) To configure the check to use only 'allowPublicFinalFields' option: 


```xml
<module name="VisibilityModifier">
  <property name="allowPublicFinalFields" value="true"/>
</module>
```
        

Code example: 


```java
public class InputPublicImmutable {
  public final int someIntValue;
  public final ImmutableSet<String> includes;
  public final java.lang.String notes;
  public final BigDecimal value;
  public final List list;
 

  public InputPublicImmutable(Collection<String> includes,
        BigDecimal value, String notes, int someValue, List l) {
    this.includes = ImmutableSet.copyOf(includes);
    this.value = value;
    this.notes = notes;
    this.someIntValue = someValue;
    this.list = l;
  }
}
```

## Further Reading

* [checkstyle - VisibilityModifier](http://checkstyle.sourceforge.net/config_design.html#VisibilityModifier)
