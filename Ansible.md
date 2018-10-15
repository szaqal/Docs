# Ansible 

### Test connectivity

```
[root@localhost openshift-ansible]# ansible -i inventory/hosts.localhost all -m  ping 
localhost | SUCCESS => {
    "changed": false, 
    "ping": "pong"
}

```

### Ask for password instead of ssh auth + sudo w/o parssword

```
 ansible-playbook playbook.yml --sudo  --ask-pass --ask-sudo-pass
```
