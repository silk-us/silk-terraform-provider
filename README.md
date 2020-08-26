# Silk Terraform Provider

- Website: https://www.terraform.io
- [![Gitter chat](https://badges.gitter.im/hashicorp-terraform/Lobby.png)](https://gitter.im/hashicorp-terraform/Lobby)
- Mailing list: [Google Groups](http://groups.google.com/group/terraform-tool)

<img src="https://cdn.rawgit.com/hashicorp/terraform-website/master/content/source/assets/images/logo-hashicorp.svg" width="600px">


# Quick Start

Installation and Usage information can be found in the Silk Terraform Provider [Quick Start Guide](https://github.com/silk-us/silk-terraform-provider/blob/master/docs/quick_start.md).

# Example

```hcl
provider "silk" {}

resource "silk_volume_group" "Silk-Volume-Group" {
  name = "TerraformVolumeGroup"
  quota_in_gb = 30
  enable_deduplication = true
  description = "Crated through TF"
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