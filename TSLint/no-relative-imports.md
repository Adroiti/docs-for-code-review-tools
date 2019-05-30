Pattern: Use of relative import

Issue: -

## Description

Do not use relative paths when importing external modules or ES6 import
declarations. The advantages of removing all relative paths from imports
is that:
-   The import name will be consistent across all files and
    subdirectories so searching for usages is much easier.
-   Moving source files to different folders will not require you to
    edit your import statements.
-   3) It will be possible to copy and paste import lines between files
    regardless of the file location.
-   4) version control diffs will be simplified by having overall fewer
    edits to the import lines.
	
Option `allow-siblings` can be passed to allow relative imports for files in the same or nested folders.

## Further Reading

* [TSLint - no-relative-imports](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)