Pattern: Disabled in-transit encryption for AWS MSK cluster

Issue: -

## Description

Encryption should be forced for Kafka clusters, including for communication between nodes. This ensure sensitive data is kept private.

**Resolution**: Enable in transit encryption.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_msk_cluster" "bad_example" {
	encryption_info {
		encryption_in_transit {
			client_broker = "TLS_PLAINTEXT"
			in_cluster = true
		}
	}
}
```

Example of **correct** code:

```terraform
resource "aws_msk_cluster" "good_example" {
	encryption_info {
		encryption_in_transit {
			client_broker = "TLS"
			in_cluster = true
		}
	}
}
```