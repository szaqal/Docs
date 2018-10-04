# Ansible 

### Test connectivity

```
[root@localhost openshift-ansible]# ansible -i inventory/hosts.localhost all -m  ping 
localhost | SUCCESS => {
    "changed": false, 
    "ping": "pong"
}

```
