Pattern: Wrong key order in properties file

Issue: -

## Description

Detects if keys in properties files are in correct order. 

Rationale: Sorted properties make it easy for people to find required properties by name in file. It makes merges more easy. While there are no errors at runtime. This check is valuable only on files with string resources where order of lines does not matter at all, but this can be improved. 

Known limitation: The key should not contain a newline. The string compare will work, but not the line number reporting. 

## Examples

To configure the check: 
       

    <module name="OrderedProperties"/>

            

Example properties file: 


    A =65

    a =97

    key =107 than nothing

    key.sub =k is 107 and dot is 46

    key.png =value - violation

            

We check order of key's only. Here we would like to use an Locale independent order mechanism, an binary order. The order is case insensitive and ascending. 

  - The capital A is on 65 and the lowercase a is on position 97 on the ASCII table. 
  - Key and key.sub are in correct order here, because only keys are relevant. Therefore on line 5 you have only "key" an nothing behind. On line 6 you have "key." The dot is on position 46 which is higher than nothing. key.png will reported as violation because "png" comes before "sub".

## Further Reading

* [checkstyle - OrderedProperties](https://checkstyle.sourceforge.io/checks/misc/orderedproperties.html)