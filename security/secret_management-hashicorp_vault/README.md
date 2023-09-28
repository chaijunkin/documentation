# Bootstrap

## Pre-requisite

- Step 1: Enable Enable AppRole auth method using root account
  - Enter http://127.0.0.1:8200/ui in a browser to launch the Vault UI.
  - Enter root in the Token field and click Sign In.
  - Select the Access tab on top.
  - Select Enable new method.
  - Enable AppRole
  - Select the AppRole radio button and click Next.
  - Leave the path as the defaulted path and click Enable Method.
  - Select approle without making any update.

- Step 2: Create the role for role-id and secret-id
  - vault write auth/approle/role/vaultwarden token_policies="read-policy"
      Example Demo:
          0ac41e73-0cf6-eaa0-ed22-c5dc19926a6f
  - vault write -force auth/approle/role/vaultwarden/secret-id
      Example Demo:
          Key                Value
          secret_id          b76f927b-3947-beb2-1fbc-93d23ee37b4f
          secret_id_accessor afe460b1-87d5-7660-4e67-0abf01a5c0d9
          secret_id_num_uses 0
          secret_id_ttl      0
  - ROLEID=<YOUR ROLE ID>
    SECRETID=<YOUR SECRET ID >
    vault write auth/approle/login role_id="${ROLEID}" secret_id="${SECRETID}"
    vault write auth/approle/login role_id="0ac41e73-0cf6-eaa0-ed22-c5dc19926a6f" secret_id="781a96c3-967f-de16-babf-52c3de099a5b"

## Reference

- Vault preparation for ESO https://medium.com/@tiwarisan/hashicorp-vault-install-on-kubernetes-enable-and-use-approle-5172f1eefe18
