Pattern: Use of suspicious file inclusion

Issue: -

## Description

Checks that `__DIR__`, `dirname( __FILE__ )` or `plugin_dir_path( __FILE__ )` are used when including or requiring files.

## Further Reading

* [WordPressVIPMinimum.Files.IncludingFile](https://github.com/Automattic/VIP-Coding-Standards/tree/develop/WordPressVIPMinimum/Sniffs/Files/IncludingFileSniff.php)