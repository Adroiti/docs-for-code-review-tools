Pattern: Missing trailing comma in array initialization

Issue: -

## Description

Checks that array initialization contains a trailing comma. 


```java
int[] a = new int[]
{
    1,
    2,
    3,
};
```
        

The check demands a comma at the end if neither left nor right curly braces are on the same line as the last element of the array. 


```java
return new int[] { 0 };
return new int[] { 0
    };
return new int[] {
    0 };
```
        

Rationale: Putting this comma in makes it easier to change the order of the elements or add new elements on the end. Main benefit of a trailing comma is that when you add new entry to an array, no surrounding lines are changed. 


```java
{
    100000000000000000000,
    200000000000000000000, // OK
}
 

{
    100000000000000000000,
    200000000000000000000,
    300000000000000000000,  // Just this line added, no other changes
}
```
        

If closing brace is on the same line as training comma, this benefit is gone (as the check does not demand a certain location of curly braces the following two cases will not produce a violation): 


```java
{100000000000000000000,
    200000000000000000000,} // Trailing comma not needed, line needs to be modified anyway
 

{100000000000000000000,
    200000000000000000000, // Modified line
    300000000000000000000,} // Added line
```
        

If opening brace is on the same line as training comma there's also (more arguable) problem: 


```java
{100000000000000000000, // Line cannot be just duplicated to slightly modify entry
}
 

{100000000000000000000,
    100000000000000000001, // More work needed to duplicate
}
```
        

## Examples

To configure the check: 


```java
   <module name="ArrayTrailingComma"/>
```
 

Which results in the following violations: 


```java
   int[] numbers = {1, 2, 3};    //no violation
   boolean[] bools = {
   true,
   true,
   false
   };    //violation
 

   String[][] text = {{},{},};    //no violation
 

   double[][] decimals = {
   {0.5, 2.3, 1.1,},    //no violation
   {1.7, 1.9, 0.6},
   {0.8, 7.4, 6.5}
   };    // violation as previous line misses a comma
 

   char[] chars = {'a', 'b', 'c'
   };        / /no violation
 

   String[] letters = {
   "a", "b", "c"};        // no violation
 

   int[] a1 = new int[]{
   1,
   2
   ,
   };    // no violation
 

   int[] a2 = new int[]{
   1,
   2
   ,};        // no violation
```

## Further Reading

* [checkstyle - ArrayTrailingComma](http://checkstyle.sourceforge.net/config_coding.html#ArrayTrailingComma)
