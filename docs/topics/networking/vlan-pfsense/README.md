# Diaoul
I have Guest, LAN for regular stuff, Management, Server, Video and Things
Things don't have internet, could've called that one nift: No Internet for Things. I get that you have a similar setup with IoT being unable to reach the internet

# onedr0p

my current vlans are 

iot: devices that only need access to internet, or media players that have a firewall rule open to plex ip:port

these devices cannot communicate with each other

guest: my wife's wifi and anyone who visits, firewall rules allow to talk to the iot network so chromecast works

wireguard: open to all vlans, might be more walled off in the future

management: unifi switches, cloud key, nas, cameras, also not walled off to any other vlan

k8s: kubernetes nodes, also not walled off to any other vlan

# bjw-s
Currently I have management , guest, IoT , but thinking of adding trusted  and servers  to that list

