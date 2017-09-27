Pattern: Missing class Javadoc

Issue: -

## Description

Makes sure each class and interface definition is preceded by Javadoc. Enum definitions are not checked, due to strange behavior in the Groovy AST. 

By default, only the main class in a file is checked for Javadoc. The main class is defined as the class that has the same name as the source file, for instance `SomeClass` is the main class in `SomeClass.groovy` but the class `SomeOtherClass` defined in the same source file is not the main class. To check all the classes in the file set the rule property `applyToNonMainClasses` to `true`.

## Further Reading

* [CodeNarc - ClassJavadoc](http://codenarc.sourceforge.net/codenarc-rules-formatting.html#ClassJavadoc)