Pattern: .NET Assembly is not optimized

Issue: -

## Description

This file was not optimized by .NET compiler. Optimizations make your output file smaller, faster, and more efficient. However, they result in code rearrangement in the output file, which can make debugging difficult. So typically optimizations should be disabled for debugging and enabled for publishing an assembly.

## Further Reading

* [MSDN Library - How to: Set Debug and Release Configurations](https://docs.microsoft.com/en-us/visualstudio/debugger/how-to-set-debug-and-release-configurations)
* [MSDN Library - C# Reference - /optimize](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/compiler-options/optimize-compiler-option)
