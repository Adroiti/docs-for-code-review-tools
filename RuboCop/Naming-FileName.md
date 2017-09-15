Pattern: Invalid file name

Issue: -

## Description

This cop makes sure that Ruby source files have `snake_case` names. Ruby scripts (i.e. source files with a shebang in the first line) are ignored.

## Default configuration

Attribute | Value
--- | ---
Exclude |
ExpectMatchingDefinition | false
Regex |
IgnoreExecutableScripts | true
AllowedAcronyms | CLI, DSL, ACL, API, ASCII, CPU, CSS, DNS, EOF, GUID, HTML, HTTP, HTTPS, ID, IP, JSON, LHS, QPS, RAM, RHS, RPC, SLA, SMTP, SQL, SSH, TCP, TLS, TTL, UDP, UI, UID, UUID, URI, URL, UTF8, VM, XML, XMPP, XSRF, XSS

## Further Reading

* [RuboCop - Naming/FileName](https://rubocop.readthedocs.io/en/latest/cops_naming/#namingfilename)
* [https://github.com/bbatsov/ruby-style-guide#snake-case-files](https://github.com/bbatsov/ruby-style-guide#snake-case-files)
