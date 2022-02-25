Pattern: Enabled logging of statements for Google PostgreSQL

Issue: -

## Description

Logging of statements which could contain sensitive data is not advised, therefore this setting should preclude all statements from being logged.

**Resolution**: Disable minimum duration statement logging completely.

## Examples

Example of **incorrect** code:

```terraform
resource "google_sql_database_instance" "db" {
	name             = "db"
	database_version = "POSTGRES_12"
	region           = "us-central1"
	settings {
		database_flags {
			name  = "log_min_duration_statement"
			value = "99"
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
			name  = "log_min_duration_statement"
			value = "-1"
		}
	}
}
```