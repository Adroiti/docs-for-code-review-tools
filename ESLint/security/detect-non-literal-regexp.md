Pattern: Use of `RegExp(variable)`

Issue: -

## Description

Detects `RegExp(variable)`, which might allow an attacker to DOS your server with a long-running regular expression.