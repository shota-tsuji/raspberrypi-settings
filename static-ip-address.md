```bash
# find dedicated ip address (use tab completion)
ip addr show

# find default gateway id address
ip route show

# find dns id address
grep "nameserver" /etc/resolv.conf
```

```bash
# install dhcpcd5
sudo apt install dhcpcd5

# find setting file
dpkg -L dhcpcd5

sudo vim /etc/dhcpcd.conf

interface xxx
static ip_address=<static ip address>/<subnet mask>
static routers=<dhcp server ip address>
static domain_name_server=<dns server ip address>
```

set client's `/etc/hosts`
```bash
# ex.) 192.168.11.253 linux-server
<static ip address> <server alias>
```
