Pattern: Access to `java.io` package

Issue: -

## Description

This rule reports violations of the Enterprise JavaBeans specification by using the `java.io` package to access files or the file system.

In this case, the program violates the following (Enterprise JavaBeans) EJB guideline: `An enterprise bean must not use the java.io package to attempt to access files and directories in the file system.`

A requirement that the specification justifies in the following way: "The file system APIs are not well-suited for business components to access data. Business components should use a resource manager API, such as JDBC, to store data."

Example of violations:

``` groovy
FileSystem.getFileSystem()          // any method on FileSystem
FileSystem.fileSystem.delete(aFile) // property access of FileSystem

// shouldn't create files
new File(name)
new File(name, parent)

// don't create file readers
new FileReader(name)

// don't create file output streams
new FileOutputStream(name)
new FileOutputStream(name, true)

// don't create random access file
new RandomAccessFile(name, parent)
```

## Further Reading

* [CodeNarc - JavaIoPackageAccess](http://codenarc.sourceforge.net/codenarc-rules-security.html#JavaIoPackageAccess)