Pattern: Insecure node metadata for GKE

Issue: -

## Description

If the `workload_metadata_config` block within `node_config` is included, the `node_metadata` attribute should be configured securely.

The attribute should be set to `SECURE` to use metadata concealment, or `GKE_METADATA_SERVER` if workload identity is enabled. This ensures that the VM metadata is not unnecessarily exposed to pods.

**Resolution**: Set node metadata to `SECURE` or `GKE_METADATA_SERVER`.

## Examples

Example of **incorrect** code:

```terraform
resource "google_container_node_pool" "bad_example" {
	node_config {
		workload_metadata_config {
			node_metadata = "EXPOSE"
		}
	}
}
```

Example of **correct** code:

```terraform
resource "google_container_node_pool" "good_example" {
	node_config {
		workload_metadata_config {
			node_metadata = "SECURE"
		}
	}
}
```