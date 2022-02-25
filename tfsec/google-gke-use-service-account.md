Pattern: Missing service account for GKE node

Issue: -

## Description

You should create and use a minimally privileged service account to run your GKE cluster instead of using the Compute Engine default service account.

**Resolution**: Use limited permissions for service accounts to be effective.

## Examples

Example of **incorrect** code:

```terraform
resource "google_container_cluster" "bad_example" {
	node_config {
	}
}
```

Example of **correct** code:

```terraform
resource "google_container_cluster" "good_example" {
	node_config {
		service_account = "cool-service-account@example.com"
	}
}
```