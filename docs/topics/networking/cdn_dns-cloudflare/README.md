# Getting started
wget -q https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-x86_64.rpm
rpm -Uvh cloudflared-linux-x86_64.rpm
sudo yum install cloudflared


## Next
cloudflared tunnel login
- Copy the URL on browser
- Authorized

cloudflared tunnel create cloudjur-cloudflare-tunnel

Tunnel credentials written to /home/linux/.cloudflared/4549017c-6edc-4ca3-8546-7788f4f6bede.json. cloudflared chose this file based on where your origin certificate was found. Keep this file secret. To revoke these credentials, delete the tunnel.

Created tunnel cloudjur-cloudflare-tunnel with id 4549017c-6edc-4ca3-8546-7788f4f6bede