# Silk Terraform Provider

- Website: https://www.terraform.io
- [![Gitter chat](https://badges.gitter.im/hashicorp-terraform/Lobby.png)](https://gitter.im/hashicorp-terraform/Lobby)
- Mailing list: [Google Groups](http://groups.google.com/group/terraform-tool)

<img src="https://cdn.rawgit.com/hashicorp/terraform-website/master/content/source/assets/images/logo-hashicorp.svg" width="600px">


# Quick Start

Installation and Usage information can be found in the Silk Terraform Provider [Quick Start Guide](https://github.com/silk-us/silk-terraform-provider/blob/master/docs/quick_start.md).

# Example

```hcl
provider "silk" {
  server = "10.0.10.10"
  username = "admin"
  password = "password"
}

variable "vm-name" {
    type = string
    default = "test"
}
variable "vg-name" {
    type = string
    default = "-vg"
}

variable "vol01-name" {
    type = string
    default = "-vol-01"
}

resource "silk_volume" "Silk-Volume" {
  name = "${var.vm-name}${var.vol01-name}"
  size_in_gb = 100
  volume_group_name = silk_volume_group.Silk-Volume-Group.name
  description = "Build with TF"
  host_mapping = [silk_host.Silk-Host.name]
  allow_destroy = true
}

resource "silk_volume_group" "Silk-Volume-Group" {
  name = "${var.vm-name}${var.vg-name}"
  quota_in_gb = 0
  enable_deduplication = false
  description = "Crated through TF"
}

resource "silk_host" "Silk-Host" {
  name = var.vm-name
  host_type = "Linux"
  iqn = "iqn.1994-05.com.redhat:9fe73c6123a6"
}
```
# Documentation

* [Provider](https://github.com/silk-us/silk-terraform-provider/tree/master/docs)
* [silk_host](https://github.com/silk-us/silk-terraform-provider/blob/master/docs/silk_host.md)
* [silk_host_group](https://github.com/silk-us/silk-terraform-provider/blob/master/docs/silk_host_group.md)
* [silk_volume](https://github.com/silk-us/silk-terraform-provider/blob/master/docs/silk_volume.md)
* [silk_volume_group](https://github.com/silk-us/silk-terraform-provider/blob/master/docs/silk_volume_group.md)
* [silk_retention_policy](https://github.com/silk-us/silk-terraform-provider/blob/master/docs/silk_retention_policy.md)
* [silk_capacity_policy](https://github.com/silk-us/silk-terraform-provider/blob/master/docs/silk_capacity_policy.md)