---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "vmmanager6_vm_qemu Resource - terraform-provider-vmmanager6"
subcategory: ""
description: |-
  
---

# vmmanager6_vm_qemu (Resource)





<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `domain` (String) Domain for VM's ip addresses and hostname
- `name` (String) The VM name
- `os` (Number) VMmanager 6 template id
- `password` (String, Sensitive) Password for VM

### Optional

- `account` (Number) VMmanager user id
- `cluster` (Number) VMmanager 6 cluster id
- `cores` (Number) Number of vCPU's for VM
- `cpu_mode` (String) Cpu mode. Can be default, host-model, host-passthrough
- `custom_interfaces` (Block List) You can set some ip address manually (use ip_name) or using pool id (ip_pool) (see [below for nested schema](#nestedblock--custom_interfaces))
- `desc` (String) The VM description
- `disk` (Number) Disk Size of VM in Megabytes
- `disk_id` (Number) Internal variable. Main disk ID of VM
- `id` (String) The ID of this resource.
- `ipv4_number` (Number) Number of ipv4 addresses
- `ipv4_pools` (List of Number) VMmanager ip pools, to use for ip assignment
- `memory` (Number) RAM Size of VM in Megabytes
- `preset` (Number) id of VM preset. Preset will overwrite your cpu/mem/disk settings
- `recipes` (Block List) Array of recipes and params (see [below for nested schema](#nestedblock--recipes))
- `vxlan` (Block List) Use vxlan to create VM in local network without public ips, or mix it with custom_interfaces (see [below for nested schema](#nestedblock--vxlan))

### Read-Only

- `ip_addresses` (List of Object) Internal. List of vms ip addresses (see [below for nested schema](#nestedatt--ip_addresses))

<a id="nestedblock--custom_interfaces"></a>
### Nested Schema for `custom_interfaces`

Optional:

- `bridge` (String) Bridge name for interface
- `ip_count` (Number) How many ips add to this interface from ip_pool
- `ip_name` (String) Ip address to apply
- `ippool` (Number) Pool of ip addresses to apply


<a id="nestedblock--recipes"></a>
### Nested Schema for `recipes`

Required:

- `recipe` (Number) id of recipe

Optional:

- `recipe_params` (Block List) Array of recipe params (see [below for nested schema](#nestedblock--recipes--recipe_params))

<a id="nestedblock--recipes--recipe_params"></a>
### Nested Schema for `recipes.recipe_params`

Required:

- `name` (String) param name
- `value` (String) param value



<a id="nestedblock--vxlan"></a>
### Nested Schema for `vxlan`

Required:

- `id` (Number) id of VxLAN
- `ipnet` (Number) id of network inside VxLAN

Optional:

- `ipv4_number` (Number) How many ips from VxLAN needed


<a id="nestedatt--ip_addresses"></a>
### Nested Schema for `ip_addresses`

Read-Only:

- `addr` (String)
- `domain` (String)
- `family` (Number)
- `gateway` (String)
- `id` (Number)
- `mask` (String)
- `netid` (Number)


