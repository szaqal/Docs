#Openshift 


### Installing dependencies

```
yum update -y && yum install -y install epel-release && yum install -y vim net-tools python pip
```

* Ansible default installation 2.4 is too old

```
pip install --upgrade pip
pip install ansible=2.6.2
``` 

* Set SELinux to **permissive** mode

### Running prerequisites playbook

Checkout tag ```git checkout tags/v3.10.0 -b v3.10.0```

Run prerequisites playbook ```ansible-playbook -i inventory/hosts.localhost  playbooks/prerequisites.yml ```

Run deployment playbook ```[root@localhost openshift-ansible]# ansible-playbook -i inventory/hosts.localhost  playbooks/deploy_cluster.yml```

Once ready navigate to ```https://192.168.2.200:8443```
