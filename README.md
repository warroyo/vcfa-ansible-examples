# VCF Automation Ansible examples

This is a collection of ansible playbooks that interact with VCF Automation using the IaaS apis. These APIs are all declarative K8s based APIs so we can use the Kubernetes Ansible module to interact with them.

* [supervisor namespace](./supervisor_namespace/) - creates a simple supervsior namespace
* [virtual machine](./virtualmachine/) - creates a simple virtual machine in a supervisor namespace


## Common setup

### Setup a venv
After cloning this repo setup a python venv. If you already have ansible setup you can skip this step and just update the playbook as needed. 

```bash
python3 -m venv ./venv
source venv/bin/activate
```

### Add the token module

Some of these playbooks make use of a custom module that you can find [here](https://github.com/warroyo/vcfa-token-ansible-module). This module handles getting an access token for using the IaaS apis from VCF-A and then is passed to the kubernetes module for authentication.

1. get your ansible module path

```bash
 ansible-config dump |grep DEFAULT_MODULE_PATH
```


2. copy the module to the modules path
```bash 
git clone https://github.com/warroyo/vcfa-token-ansible-module
cd vcfa-token-ansible-module
cp vcfa_auth.py <one of the paths output above>
```