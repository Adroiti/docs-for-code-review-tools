Pattern: Disabled OS Login at project level

Issue: -

## Description

OS Login automatically revokes the relevant SSH keys when an IAM user has their access revoked.

**Resolution**: Enable OS Login at project level.

## Examples

Example of **incorrect** code:

```terraform
resource "google_compute_project_metadata" "default" {
  metadata = {
	enable-oslogin = false
  }
}
```

Example of **correct** code:

```terraform
resource "google_compute_project_metadata" "default" {
  metadata = {
    enable-oslogin = true
  }
}
```