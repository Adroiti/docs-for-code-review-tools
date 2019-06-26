Pattern: Use of session variable

Issue: -

## Description

Discourages the use of the session variable. Creating a session writes a file to the server and is unreliable in a multi-server environment.

## Further Reading

* [WordPress.VIP.SessionVariableUsage](https://lobby.vip.wordpress.com/wordpress-com-documentation/code-review-what-we-look-for/#session-start-and-other-session-functions)
* [WordPress.VIP.SessionVariableUsage](https://github.com/WordPress/WordPress-Coding-Standards/tree/develop/WordPress/Sniffs/VIP/SessionVariableUsageSniff.php)