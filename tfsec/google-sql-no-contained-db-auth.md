Pattern: Use of contained SQL database authentication

Issue: -

## Description

Users with ALTER permissions on users can grant access to a contained database without the knowledge of an administrator.

**Resolution**: Disable contained database authentication.

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
		    name  = "contained database authentication"
		    value = "off"
		}
	}
}
```