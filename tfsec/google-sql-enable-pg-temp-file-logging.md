Pattern: Disabled temporary file logging for SQL DB

Issue: -

## Description

**Resolution**: Enable temporary file logging for all files.

## Examples

Example of **incorrect** code:

```terraform
resource "google_sql_database_instance" "db" {
	name             = "db"
	database_version = "POSTGRES_12"
	region           = "us-central1"
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
		    name  = "log_temp_files"
		    value = "0"
		}
	}
}
```