Pattern: Enabled legacy ABAC permissions for GKE

Issue: -

## Description

You should disable Attribute-Based Access Control (ABAC), and instead use Role-Based Access Control (RBAC) in GKE.

RBAC has significant security advantages and is now stable in Kubernetes, so it’s time to disable ABAC.

**Resolution**: Switch to using RBAC permissions.

## Examples

Example of **incorrect** code:

```terraform
resource "google_container_cluster" "bad_example" {
	enable_legacy_abac = "true"
}
```

Example of **correct** code:

```terraform
resource "google_container_cluster" "good_example" {
	# ...
	# enable_legacy_abac not set
	# ...
}
```