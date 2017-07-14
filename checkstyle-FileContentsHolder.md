Pattern: Holds the current file contents for global access when configured as a TreeWalker sub-module

Issue: -

## Description

Holds the current file contents for global access when configured as a TreeWalker sub-module. For example,a filter can access the current file contents through this module. 

## Examples

This check should not be used by itself, as it does no reporting. It is to be used in conjunction with other checks like [SuppressionCommentFilter](config_filters.html#SuppressionCommentFilter) and [SuppressWithNearbyCommentFilter](config_filters.html#SuppressWithNearbyCommentFilter).

## Further Reading

* [checkstyle - FileContentsHolder](http://checkstyle.sourceforge.net/config_misc.html#FileContentsHolder)