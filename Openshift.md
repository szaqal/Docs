#Openshift 


### Installing dependencies

* Ansible default installation 2.4 is too old

```
pip install --upgrade pip
pip install ansible=2.6.2
``` 
* 

### Running prerequisites playbook

Checkout tag ```git checkout tags/v3.10.0 -b v3.10.0```

Run prerequisites playbook ```ansible-playbook -i inventory/hosts.localhost  playbooks/prerequisites.yml ```
