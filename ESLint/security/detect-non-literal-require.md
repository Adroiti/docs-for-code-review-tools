Pattern: Use of `require(variable)`

Issue: -

## Description

Detects `require(variable)`, which might allow an attacker to load and run arbitrary code, or access arbitrary files on disk.