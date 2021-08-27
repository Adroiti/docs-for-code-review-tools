Pattern: Disabled shielded VM for instance

Issue: -

## Description

A Shielded VM is a VM with enhanced defences/detection for rootkits/bootkits.

**Resolution**: Enable Shielded VM.

## Examples

Example of **incorrect** code:

```terraform
resource "google_compute_instance" "bad_example" {
  name         = "test"
  machine_type = "e2-medium"
  zone         = "us-central1-a"

  tags = ["foo", "bar"]

  boot_disk {
    initialize_params {
      image = "debian-cloud/debian-9"
    }
  }

  // Local SSD disk
  scratch_disk {
    interface = "SCSI"
  }

  shielded_instance_config {
    enable_vtpm = false
    enable_integrity_monitoring = false
  }
}
```

Example of **correct** code:

```terraform
resource "google_compute_instance" "bad_example" {
  name         = "test"
  machine_type = "e2-medium"
  zone         = "us-central1-a"

  tags = ["foo", "bar"]

  boot_disk {
    initialize_params {
      image = "debian-cloud/debian-9"
    }
  }

  // Local SSD disk
  scratch_disk {
    interface = "SCSI"
  }

  shielded_instance_config {
    enable_vtpm = true
    enable_integrity_monitoring = true
  }
}
```