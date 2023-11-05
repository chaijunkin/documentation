## add backport package - Debian Backports provides new packages with new features on supported Debian stable releases.
vi /etc/apt/sources.list
deb http://deb.debian.org/debian bullseye-backports main contrib
apt update && apt full-upgrade
apt install -t bullseye-backports cockpit --no-install-recommends

## Access
cockpit is hosted on <container_host>:9090

## download cockpit related package
wget https://github.com/45Drives/cockpit-identities/releases/download/v0.1.12/cockpit-identities_0.1.12-1focal_all.deb
wget https://github.com/45Drives/cockpit-file-sharing/releases/download/v3.3.4/cockpit-file-sharing_3.3.4-1focal_all.deb
wget https://github.com/45Drives/cockpit-navigator/releases/download/v0.5.10/cockpit-navigator_0.5.10-1focal_all.deb
apt install ./*.deb
rm *.deb.1
rm *.deb

Reference:
https://github.com/45Drives/cockpit-identities/releases/tag/v0.1.12
