wpa_cli

## list
list_networks

## add
add_network
set_network 1 ssid "XXX"
set_network 1 psk "XXX"
enable_network 1
save_config
quit

## delete
list_networks
remove_network 1
save_config
quit

## others
wpa_cli -i wlan0 select_network $(wpa_cli -i wlan0 list_networks | grep XXX | cut -f 1)

## test
```
nmcli connection modify <CHECK VALUE BELOW>

[connection, 802-11-wireless (wifi), 802-11-wireless-security (wifi-sec), 802-1x, ethtool, match, ipv4, ipv6, hostname, tc, proxy].
```


### use raspi-config

1 - system config