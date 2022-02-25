Pattern: Disabled checkpoints logging for Google PostgreSQL

Issue: -

## Description

Logging checkpoints provides useful diagnostic data, which can identify performance issues in an application and potential DoS vectors.

**Resolution**: Enable checkpoints logging.

## Examples

Example of **incorrect** code:

```terraform
resource "google_sql_database_instance" "db" {
	name             = "db"
	database_version = "POSTGRES_12"
	region           = "us-central1"
	settings {
		database_flags {
			name  = "log_checkpoints"
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
			name  = "log_checkpoints"
			value = "on"
		}
	}
}
```