Pattern: Disabled automated backups for SQL DB

Issue: -

## Description

Automated backups are not enabled by default. Backups are an easy way to restore data in a corruption or data-loss scenario.

**Resolution**: Enable automated backups.

## Examples

Example of **incorrect** code:

```terraform
resource "google_sql_database_instance" "db" {
	name             = "db"
	database_version = "POSTGRES_12"
	region           = "us-central1"
	settings {
		backup_configuration {
			enabled = false
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
		backup_configuration {
			enabled = true
		}
	}
}
```