# Workflow enhancement

This folder will guide you how to improve development workflow.

## Tools

- Nix
- Fish

## Get started

Bootstrap in WSL

### WSL environment configuration

Add these lines to the /etc/wsl.conf (note you will need to run your editor with sudo privileges, e.g: sudo nano /etc/wsl.conf):

```
[boot]
systemd=true
```

### Nix Installation

```
sh <(curl -L https://nixos.org/nix/install) --daemon
```


### Nix configuration

nix --experimental-features 'nix-command flakes' develop --command true

