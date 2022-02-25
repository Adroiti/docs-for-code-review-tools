Pattern: Use of cross-database ownership chaining for Google SQL

Issue: -

## Description

Cross-database ownership chaining, also known as cross-database chaining, is a security feature of SQL Server that allows users of databases access to other databases besides the one they are currently using.

**Resolution**: Disable cross database ownership chaining.

## Examples

Example of **incorrect** code:

```terraform
resource "google_sql_database_instance" "db" {
	name             = "db"
	database_version = "SQLSERVER_2017_STANDARD"
	region           = "us-central1"
}
```

Example of **correct** code:

```terraform
resource "google_sql_database_instance" "db" {
	name             = "db"
	database_version = "SQLSERVER_2017_STANDARD"
	region           = "us-central1"
	settings {
	    database_flags {
		    name  = "cross db ownership chaining"
		    value = "off"
		}
	}
}
```