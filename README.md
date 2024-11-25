<!-- BEGIN_TF_DOCS -->
## Requirements

The following requirements are needed by this module:

- <a name="requirement_proxmox"></a> [proxmox](#requirement\_proxmox) (3.0.1-rc4)

## Providers

The following providers are used by this module:

- <a name="provider_local"></a> [local](#provider\_local)

- <a name="provider_proxmox"></a> [proxmox](#provider\_proxmox) (3.0.1-rc4)

## Resources

The following resources are used by this module:

- [local_file.cluster_userdata](https://registry.terraform.io/providers/hashicorp/local/latest/docs/resources/file) (resource)
- [proxmox_vm_qemu.cluster_vm](https://registry.terraform.io/providers/Telmate/proxmox/3.0.1-rc4/docs/resources/vm_qemu) (resource)

## Required Inputs

The following input variables are required:

### <a name="input_ip_config"></a> [ip\_config](#input\_ip\_config)

Description: n/a

Type: `string`

### <a name="input_proxmox_ssh_config"></a> [proxmox\_ssh\_config](#input\_proxmox\_ssh\_config)

Description: n/a

Type:

```hcl
object({
    ssh_user     = string
    ssh_password = string
    ssh_host     = string
  })
```

### <a name="input_userdata_content"></a> [userdata\_content](#input\_userdata\_content)

Description: n/a

Type: `string`

### <a name="input_userdata_location"></a> [userdata\_location](#input\_userdata\_location)

Description: n/a

Type: `string`

### <a name="input_vm_config"></a> [vm\_config](#input\_vm\_config)

Description: n/a

Type:

```hcl
object({
    memory             = optional(number, 4096)
    balloon            = optional(number, 4096)
    cores              = optional(number, 4)
    sockets            = optional(number, 1)
    disk_size_gb       = optional(number, 40)
    os_type            = optional(string, "cloud-init")
    clone              = string
    target_node        = optional(string, "pve")
    nic                = optional(string, "virtio")
    bridge             = optional(string, "vmbr0")
    disk_location      = string
    cloudinit_location = optional(string, "local-lvm")
  })
```

### <a name="input_vm_name"></a> [vm\_name](#input\_vm\_name)

Description: n/a

Type: `string`

### <a name="input_vmid"></a> [vmid](#input\_vmid)

Description: n/a

Type: `number`
<!-- END_TF_DOCS -->