Pattern: Missing error logging for Google PostgreSQL

Issue: -

## Description

Setting the minimum log severity too high will cause errors not to be logged

**Resolution**: Set the minimum log severity to at least `ERROR`.

## Examples

Example of **incorrect** code:

```terraform
resource "google_sql_database_instance" "db" {
	name             = "db"
	database_version = "POSTGRES_12"
	region           = "us-central1"
	settings {
		database_flags {
			name  = "log_min_messages"
			value = "PANIC"
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
			name  = "log_min_messages"
			value = "WARNING"
		}
	}
}
```