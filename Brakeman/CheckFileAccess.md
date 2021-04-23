Pattern: Possible file access

Issue: -

## Description

Using user input when accessing files (local or remote) will raise a warning in Brakeman. This type of vulnerability can be used to access arbitrary files on a server (including `/etc/passwd`).

## Further Reading

* [Brakeman - File Access](https://brakemanscanner.org/docs/warning_types/file_access/)