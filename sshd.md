```bash
# config as follows
sudo vim /etc/ssh/sshd_config

PasswordAuthentication yes

# validation (If you see `Could not load host key:...` errors, let's skip and ignore them until ssh login fails.)
sshd -t

# restart sshd service
sudo systemctl restart sshd
sudo systemctl status sshd
```

### Client's prepare
```bash
# prepare key-pair to register
$ssh-keygen -t ed25519 -C "shota-tsuji <server name>" -f ~/.ssh/id_ed25519_<server name>_2022H2

# dry-run
$ssh-copy-id -n -i ~/.ssh/id_ed25519_server-01_2022H2.pub shota@server-01
...
/usr/bin/ssh-copy-id: INFO: 1 key(s) remain to be installed -- if you are prompted now it is to install the new keys
=-=-=-=-=-=-=-=
Would have added the following key(s):

ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIJZx7+eKqtR25JXVidkXlQnyoqXfUgPCkwfPMicWci5f shota-tsuji server-01
=-=-=-=-=-=-=-=

# run
$ssh-copy-id -i ~/.ssh/id_ed25519_server-01_2022H2.pub shota@server-01
/usr/bin/ssh-copy-id: INFO: Source of key(s) to be installed: "/Users/shota-tsuji/.ssh/id_ed25519_server-01_2022H2.pub"
/usr/bin/ssh-copy-id: INFO: attempting to log in with the new key(s), to filter out any that are already installed
/usr/bin/ssh-copy-id: INFO: 1 key(s) remain to be installed -- if you are prompted now it is to install the new keys
shota@server-01's password:

Number of key(s) added:        1

Now try logging into the machine, with:   "ssh 'shota@server-01'"
and check to make sure that only the key(s) you wanted were added.

```
