Pattern: Unused import

Issue: -

## Description

Checks for *import* statements for classes that are never referenced within the source file. Also checks static imports.

Known limitations:

-   Does not check for unused imports containing wildcards (e.g. `import org.codenarc.*`)
-   Misses unused imports if the class/alias name is contained within strings, comments or other (longer) names (i.e., if that string shows up almost anywhere within the source code).

## Further Reading

* [CodeNarc - UnusedImport](http://codenarc.sourceforge.net/codenarc-rules-imports.html#UnusedImport)