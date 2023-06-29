Pattern: Incorrect annotation location

Issue: -

## Description

Checks location of annotation on language elements. By default, check enforces to locate annotations immediately after documentation block and before target element.

Attention: Annotations among modifiers are ignored (looks like false-negative) as there might be a problem with annotations for return types 


```java
public @Nullable Long getStartTimeOrNull() { ... }
```

Such annotations are better to keep close to type. Due to limitations Checkstyle cannot examine target of annotation. 

Example: 


```java
@Override
@Nullable
public String getNameIfPresent() { ... }
```
        

## Examples

Example to allow multiple annotations on the same line 


```java
@SuppressWarnings("deprecation") @Mock DataLoader loader; // no violations
```
        

Use the following configuration: 


```xml
<module name="AnnotationLocation">
    <property name="allowSamelineMultipleAnnotations" value="true"/>
    <property name="allowSamelineSingleParameterlessAnnotation" value="false"/>
    <property name="allowSamelineParameterizedAnnotation" value="false"/>
</module>
```
        

Example to allow one single parameterless annotation on the same line 


```java
@Override public int hashCode() { ... } // no violations
@SuppressWarnings("deprecation") public int foo() { ... } // violation
```
        

Use the following configuration: 


```xml
<module name="AnnotationLocation">
    <property name="allowSamelineMultipleAnnotations" value="false"/>
    <property name="allowSamelineSingleParameterlessAnnotation" value="true"/>
    <property name="allowSamelineParameterizedAnnotation" value="false"/>
</module>
```
        

Example to allow only one and only pametrized annotation on the same line 


```java
@SuppressWarnings("deprecation") DataLoader loader; // no violations
@Mock DataLoader loader; // violation
```
        

Use the following configuration: 


```xml
<module name="AnnotationLocation">
    <property name="allowSamelineMultipleAnnotations" value="false"/>
    <property name="allowSamelineSingleParameterlessAnnotation" value="false"/>
    <property name="allowSamelineParameterizedAnnotation" value="true"/>
</module>
```
        

The following example demonstrates how the check validates annotations of method parameters, catch parameters, foreach, for-loop variable definitions. 

Configuration:


```xml
<module name="AnnotationLocation">
    <property name="allowSamelineMultipleAnnotations" value="false"/>
    <property name="allowSamelineSingleParameterlessAnnotation" value="false"/>
    <property name="allowSamelineParameterizedAnnotation" value="false"/>
    <property name="tokens" value="VARIABLE_DEF, PARAMETER_DEF"/>
 </module>
```
       

Code example:


```java
public void test(@MyAnnotation String s) { // OK
  ...
  for (@MyAnnotation char c : s.toCharArray()) { ... }  // OK
  ...
  try { ... }
  catch (@MyAnnotation Exception ex) { ... } // OK
  ...
  for (@MyAnnotation int i = 0; i < 10; i++) { ... } // OK
  ...
  MathOperation c = (@MyAnnotation int a, @MyAnnotation int b) -> a + b; // OK
  ...
}
```

## Further Reading

* [checkstyle - AnnotationLocation](https://checkstyle.sourceforge.io/checks/annotation/annotationlocation.html#AnnotationLocation)
