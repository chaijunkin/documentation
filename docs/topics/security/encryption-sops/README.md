
## sops operation
sops --encrypt --in-place ./kubernetes/apps/kube-system/external-secrets/bitwarden/secret.sops.yaml
sops --decrypt ./kubernetes/apps/kube-system/external-secrets/bitwarden/secret.sops.yaml



