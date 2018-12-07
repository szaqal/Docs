# KVM

### Increase VM memory

```
virsh # setmaxmem ion-os-mas-01 18G --config
virsh # setmem ion-os-mas-01 18G --config
```

### List pools / volumes

```
virsh # pool-list --all
virsh # vol-list libvirt
```

### Delete volume

```
virsh # vol-delete ion-os-master-01 --pool libvirt
Vol ion-os-master-01 deleted
```

## Add VCPUs

```
virsh # edit kubernetes-01  Put #<vcpu placement='static'>8</vcpu>
virsh # setvcpus --count 2 kubernetes-01
```

