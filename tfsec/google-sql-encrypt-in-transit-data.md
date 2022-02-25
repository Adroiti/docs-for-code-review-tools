Pattern: Disabled SSL enforcement for Google SQL

Issue: -

## Description

In-transit data should be encrypted so that if traffic is intercepted data will not be exposed in plain-text to attackers.

**Resolution**: Enforce SSL for all connections.

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
			require_ssl = false
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
			require_ssl = true
		}
	}
}
```