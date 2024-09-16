# Creating a virtual internal network
## Allow VMs to talk to each other
- internal network
- DHCP server to give IP addresses to the VMs
```bash
vboxmanage dhcpserver add --network=wazuhnetwork --server-ip=10.48.1.1 --lower-ip=10.38.1.110 --upper-ip=10.38.1.130
```

## Allow VMs to talk to each other and talk to the internet
