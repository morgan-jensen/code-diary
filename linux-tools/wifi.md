# Managing Wifi on Arch

## Installing Network Manager
Network manager can be installed witht he package `networkmanager`, which contains a daemon, a cli, and a curses-based interface.

## Enable NetworkManager
After installation, you should start/enable `NetworkManager.service`. Once the daemon is started it will automatically connect to any available "system connections" that have been configured.
```
systemctl start NetworkManager.service
```

## Use CLI to connect to network
List nearby networks:
```
nmcli device wifi list
```
Connect to a wifi network:
```
nmcli device wifi connect <SSID> password <password>
```
Disconnect an interface:
```
nmcli device disconnect ifname eth0
```
Activate a connection (i.e. connect to a network with an existing profile):
```
nmcli connection up <name>
```
Delete a connection:
```
nmcli connection delete <name>
```
Turn off wifi:
```
nmcli radio wifi off
```

## Using Text User Interface
```
nmtui
```
This is pretty intuitive, and doesnt require much knowledge.
