Pattern: Disabled connection logging for Google PostgreSQL

Issue: -

## Description

Logging connections provides useful diagnostic data such as session length, which can identify performance issues in an application and potential DoS vectors.

**Resolution**: Enable connection logging.

## Examples

Example of **incorrect** code:

```terraform
resource "google_sql_database_instance" "db" {
	name             = "db"
	database_version = "POSTGRES_12"
	region           = "us-central1"
	settings {
		database_flags {
			name  = "log_connections"
			value = "off"
		}
	}
}
```

Example of **correct** code:

```terraform
resource "google_sql_database_instance" "db" {
	name             = "db"
	database_version = "POSTGRES_12"
	region           = "us-central1"
	settings {
		database_flags {
			name  = "log_connections"
			value = "on"
		}
	}
}
```