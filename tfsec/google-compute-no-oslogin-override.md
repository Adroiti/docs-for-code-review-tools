Pattern: Instance overrides project setting for OS Login

Issue: -

## Description

OS Login automatically revokes the relevant SSH keys when an IAM user has their access revoked.

**Resolution**: Enable OS Login at project level and remove instance-level overrides.

## Examples

Example of **incorrect** code:

```terraform
resource "google_compute_instance" "default" {
  name         = "test"
  machine_type = "e2-medium"
  zone         = "us-central1-a"

  boot_disk {
    initialize_params {
      image = "debian-cloud/debian-9"
    }
  }

  // Local SSD disk
  scratch_disk {
    interface = "SCSI"
  }

  metadata = {
    enable-oslogin = false
  }
}
```

Example of **correct** code:

```terraform
resource "google_compute_instance" "default" {
  name         = "test"
  machine_type = "e2-medium"
  zone         = "us-central1-a"

  boot_disk {
    initialize_params {
      image = "debian-cloud/debian-9"
    }
  }

  // Local SSD disk
  scratch_disk {
    interface = "SCSI"
  }

  metadata = {
  }
}
```