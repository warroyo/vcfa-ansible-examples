# Creating a VM using Ansible and VCFA

This playbook creates a veyr basic VM using the VM service through VCFA

## Pre-reqs

* content library created in VCFA tenant
* ubuntu ova loaded into the content library
* supervisor namespace created

## Usage

1. update the playbook with any vars required in the `vars.yml` file


2. run the playbook

```bash
ansible-playbook vm.yml
```

