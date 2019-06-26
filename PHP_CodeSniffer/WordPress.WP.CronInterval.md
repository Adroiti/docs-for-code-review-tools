Pattern: Frequent cron schedule

Issue: -

## Description

Overly frequent cron events (anything less than 15 minutes) can significantly impact the performance of the site, as can cron events that are expensive.

## Further Reading

* [VIP Go](https://vip.wordpress.com/documentation/vip-go/code-review-blockers-warnings-notices/#cron-schedules-less-than-15-minutes-or-expensive-events)
* [WordPress.WP.CronInterval](https://github.com/WordPress/WordPress-Coding-Standards/tree/develop/WordPress/Sniffs/WP/CronIntervalSniff.php)