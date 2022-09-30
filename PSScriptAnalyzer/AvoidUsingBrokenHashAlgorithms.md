Pattern: Use of broken hash algorith

Issue: -

## Description

Avoid using the broken algorithms MD5 or SHA-1.

## How

Replace broken algorithms with secure alternatives. MD5 and SHA-1 should be replaced with SHA256,
SHA384, SHA512, or other safer algorithms when possible, with MD5 and SHA-1 only being utilized by necessity for backwards compatibility.

## Example 1

Example of **incorrect** code:

```powershell
Get-FileHash foo.txt -Algorithm MD5
```

Example of **correct** code:

```powershell
Get-FileHash foo.txt -Algorithm SHA256
```

## Example 2

Example of **incorrect** code:

```powershell
Get-FileHash foo.txt -Algorithm SHA1
```

Example of **correct** code:

```powershell
Get-FileHash foo.txt
```

## Further Reading

* [PSScriptAnalyzer - AvoidUsingBrokenHashAlgorithms](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/AvoidUsingBrokenHashAlgorithms.md)