Pattern: Missing use of Shielded VM Integrity Monitoring for Google Compute

Issue: -

## Description

Integrity monitoring helps you understand and make decisions about the state of your VM instances.

**Resolution**: Enable Shielded VM Integrity Monitoring.

## Examples

The following example will fail the google-compute-enable-shielded-vm-im check.
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
     enable_integrity_monitoring = false
   }
 }
 
```

The following example will pass the google-compute-enable-shielded-vm-im check.
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
     enable_integrity_monitoring = true
   }
 }
 
```

## Further reading

- [https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_instance#enable_vtpm](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_instance#enable_vtpm)
- [https://cloud.google.com/security/shielded-cloud/shielded-vm#integrity-monitoring](https://cloud.google.com/security/shielded-cloud/shielded-vm#integrity-monitoring)