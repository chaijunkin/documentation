Reset password

su -

rw

passwd root  // paste your password

## Setup Wifi - Change WIFI Static IP 
### OPTION 1
#### Step 1
nano /etc/dhcpcd.conf

#### Step 2
interface wlan0
static routers=192.168.99.1
static domain_name_servers=192.168.99.1
static ip_address=192.168.99.99/24



##### Step 5 for network SSID connection configuration
network={
ssid="chaifamily-SVC"
scan_ssid=1
key_mgmt=WPA-PSK
}

network={
ssid="chaifamily-2.4G"
scan_ssid=1
key_mgmt=WPA-PSK
}
### OTHERS
/etc/dnsmasq.d/99-k8s-gateway-forward.conf

## restart dns

<!-- ### Step 3 ip route - https://wiki.archlinux.org/title/dhcpcd
/etc/dhcpcd.exit-hook
ip route add 10.11.12.0/24 via 192.168.192.5

original
default via 192.168.1.3 dev wlan0 proto dhcp src 192.168.1.127 metric 302
192.168.1.0/24 dev wlan0 proto dhcp scope link src 192.168.1.127 metric 302

now -->


<!-- 
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
country=MY

network={

scan_ssid=1
key_mgmt=WPA-PSK
}

wpa_supplicant.conf
CREATE ssh file -->


REFERENCE:
<!-- 
#!/bin/bash

set +e

CURRENT_HOSTNAME=`cat /etc/hostname | tr -d " \t\n\r"`
if [ -f /usr/lib/raspberrypi-sys-mods/imager_custom ]; then
   /usr/lib/raspberrypi-sys-mods/imager_custom set_hostname raspberrypi
else
   echo raspberrypi >/etc/hostname
   sed -i "s/127.0.1.1.*$CURRENT_HOSTNAME/127.0.1.1\traspberrypi/g" /etc/hosts
fi
FIRSTUSER=`getent passwd 1000 | cut -d: -f1`
FIRSTUSERHOME=`getent passwd 1000 | cut -d: -f6`
if [ -f /usr/lib/raspberrypi-sys-mods/imager_custom ]; then
   /usr/lib/raspberrypi-sys-mods/imager_custom enable_ssh
else
   systemctl enable ssh
fi
if [ -f /usr/lib/userconf-pi/userconf ]; then
   /usr/lib/userconf-pi/userconf 'pi' ''
else
   echo "$FIRSTUSER:"'' | chpasswd -e
   if [ "$FIRSTUSER" != "pi" ]; then
      usermod -l "pi" "$FIRSTUSER"
      usermod -m -d "/home/pi" "pi"
      groupmod -n "pi" "$FIRSTUSER"
      if grep -q "^autologin-user=" /etc/lightdm/lightdm.conf ; then
         sed /etc/lightdm/lightdm.conf -i -e "s/^autologin-user=.*/autologin-user=pi/"
      fi
      if [ -f /etc/systemd/system/getty@tty1.service.d/autologin.conf ]; then
         sed /etc/systemd/system/getty@tty1.service.d/autologin.conf -i -e "s/$FIRSTUSER/pi/"
      fi
      if [ -f /etc/sudoers.d/010_pi-nopasswd ]; then
         sed -i "s/^$FIRSTUSER /pi /" /etc/sudoers.d/010_pi-nopasswd
      fi
   fi
fi
if [ -f /usr/lib/raspberrypi-sys-mods/imager_custom ]; then
   /usr/lib/raspberrypi-sys-mods/imager_custom set_wlan '@unifi' '' 'MY'
else
cat >/etc/wpa_supplicant/wpa_supplicant.conf <<'WPAEOF'
country=MY
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
ap_scan=1

update_config=1
network={
	ssid=
	psk=
}

WPAEOF
   chmod 600 /etc/wpa_supplicant/wpa_supplicant.conf
   rfkill unblock wifi
   for filename in /var/lib/systemd/rfkill/*:wlan ; do
       echo 0 > $filename
   done
fi
if [ -f /usr/lib/raspberrypi-sys-mods/imager_custom ]; then
   /usr/lib/raspberrypi-sys-mods/imager_custom set_keymap 'us'
   /usr/lib/raspberrypi-sys-mods/imager_custom set_timezone 'Asia/Kuala_Lumpur'
else
   rm -f /etc/localtime
   echo "Asia/Kuala_Lumpur" >/etc/timezone
   dpkg-reconfigure -f noninteractive tzdata
cat >/etc/default/keyboard <<'KBEOF'
XKBMODEL="pc105"
XKBLAYOUT="us"
XKBVARIANT=""
XKBOPTIONS=""

KBEOF
   dpkg-reconfigure -f noninteractive keyboard-configuration
fi
rm -f /boot/firstrun.sh
sed -i 's| systemd.run.*||g' /boot/cmdline.txt
exit 0 -->


apt install
net-tools
dnsutils