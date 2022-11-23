# bluetoothctl
```shell
bluetoothctl -- list
bluetoothctl -- scan on

# set at first connection (pairing)
bluetoothctl -- pair XX:XX:XX:XX:XX:XX
bluetoothctl -- trust XX:XX:XX:XX:XX:XX

# set at second time and later
bluetoothctl -- disconnect XX:XX:XX:XX:XX:XX
bluetoothctl -- connect XX:XX:XX:XX:XX:XX

# check whether it is connected
bluetoothctl -- info
```

