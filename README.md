# hosts

Static Ansible inventory repository. Contains the main `hosts` inventory file and supporting group/host variable files used across demo and lab environments.

---

## Structure

```
hosts/
└── hosts    # Static inventory file with host groups and variables
```

## Usage

Reference this repo as a **project-based inventory source** in AAP Controller:

1. Create a **Project** pointing to this repository
2. Create an **Inventory** in AAP Controller
3. Add a **Source** to the inventory, set **Source** to `Sourced from a Project`
4. Select this project and set the **Inventory file** to `hosts`

## Inventory Format

```ini
[webservers]
web01.example.com
web02.example.com

[dbservers]
db01.example.com

[all:vars]
ansible_user=ansible
ansible_become=true
```

## Notes

- Credentials (passwords, keys) should **never** be stored in this file — inject them via AAP Controller credential types
- For dynamic inventory (AWS, Azure, ServiceNow, NetBox), see the [inventoryplugins](https://github.com/redawg/inventoryplugins) repository
