Pattern: Use of public access for SQL DB

Issue: -

## Description

Database instances should be configured so that they are not available over the public internet, but to internal compute resources which access them.

**Resolution**: Remove public access from database instances.

## Examples

Example of **incorrect** code:

```terraform
resource "google_sql_database_instance" "postgres" {
	name             = "postgres-instance-a"
	database_version = "POSTGRES_11"
	
	settings {
		tier = "db-f1-micro"
	
		ip_configuration {
			ipv4_enabled = false
			authorized_networks {
				value           = "108.12.12.0/24"
				name            = "internal"
			}
	
			authorized_networks {
				value           = "0.0.0.0/0"
				name            = "internet"
			}
		}
	}
}
```

Example of **correct** code:

```terraform
resource "google_sql_database_instance" "postgres" {
	name             = "postgres-instance-a"
	database_version = "POSTGRES_11"
	
	settings {
		tier = "db-f1-micro"
	
		ip_configuration {
			ipv4_enabled = false
			authorized_networks {
				value           = "108.12.12.0/24"
				name            = "internal"
			}
		}
	}
}
```