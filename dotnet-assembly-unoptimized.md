Pattern: NET Assembly is not optimized

Issue: -

## Description

This file was not optimized by .NET compiler. Optimizations make your output file smaller, faster, and more efficient. However, they result in code rearrangement in the output file, which can make debugging difficult. So typically optimizations should be disabled for debugging and enabled for publishing an assembly.

## Further Reading

* [MSDN Library - Common Problems When Creating a Release Build](https://msdn.microsoft.com/en-us/library/dykf6bx9.aspx)
* [MSDN Library - How to: Set Debug and Release Configurations](https://msdn.microsoft.com/en-us/library/wx0123s5.aspx)
* [MSDN Library - C# Reference - /optimize](https://msdn.microsoft.com/en-us/library/t0hfscdc.aspx)
