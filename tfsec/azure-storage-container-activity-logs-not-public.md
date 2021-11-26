Pattern: Enabled Azure public access to storage container

Issue: -

## Description

Anonymous, public read access to a container and its blobs can be enabled in Azure Blob storage. It grants read-only access to these resources without sharing the account key or requiring a shared access signature.

We recommend you do not provide anonymous access to blob containers until, and unless, it is strongly desired. A shared access signature token should be used for providing controlled and timed access to blob containers.

**Resolution**: disable public access to storage containers.

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_storage_container" "bad_example" {
	name                  = "terraform-container-storage"
	container_access_type = "public"
}
```

Example of **correct** code:

```terraform
resource "azurerm_storage_container" "good_example" {
	name                  = "terraform-container-storage"
	container_access_type = "private"
}
```