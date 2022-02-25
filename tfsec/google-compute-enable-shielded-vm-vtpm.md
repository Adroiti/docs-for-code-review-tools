Pattern: Missing use of Shielded VM VTPM for Google Compute

Issue: -

## Description

The virtual TPM provides numerous security measures to your VM.

**Resolution**: Enable Shielded VM VTPM.

## Examples

The following example will fail the google-compute-enable-shielded-vm-vtpm check.
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
   }
 }
 
```

The following example will pass the google-compute-enable-shielded-vm-vtpm check.
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
   }
 }
 
```

## Further reading

- [https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_instance#enable_vtpm](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_instance#enable_vtpm)
- [https://cloud.google.com/blog/products/identity-security/virtual-trusted-platform-module-for-shielded-vms-security-in-plaintext](https://cloud.google.com/blog/products/identity-security/virtual-trusted-platform-module-for-shielded-vms-security-in-plaintext)