Pattern: Use of discouraged function for remote request

Issue: -

## Description

Use `wpcom_vip_file_get_contents()` or `vip_safe_wp_remote_get()` instead. If it's for a local file please use `WP_Filesystem` instead.

## Further Reading

* [WordPressVIPMinimum.Performance.FetchingRemoteData](https://github.com/Automattic/VIP-Coding-Standards/tree/develop/WordPressVIPMinimum/Sniffs/Performance/FetchingRemoteDataSniff.php)