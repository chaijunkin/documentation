XPC - pending checking and confirm

# Useful link
- https://github.com/dani-garcia/vaultwarden/wiki/FAQs
- vaultwarden.<`mydomain`>.tld/admin
- vaultwarden.<`mydomain`>.tld/admin/diagnostics

# Deployment
- Kubernetes
  - Helm chart (github.com/<`myusername`>/charts)

# Configuration
- / Overview
- / Disable registration of new users
- / Disable invitations
- / Enabling admin page
- / Disable the admin token
- XPC Enabling WebSocket notifications 
- NA Enabling U2F and FIDO2 WebAuthn authentication
- NA Enabling YubiKey OTP authentication
- / Changing persistent data location (attachment /, icon_cache /, database name and location NA)
- NA Changing the API request size limit
- DEFAULT Changing the number of workers
- / SMTP configuration (Remember generate application password in mail provider (e.g. Zoho) for SMTP password)
- X Password hint display
- / Disabling or overriding the Vault interface hosting
- / Logging (log level == warn, time format == %+)
- NA Creating a systemd service
- XPC Syncing users from LDAP
- NA Using an alternate base dir (subdir/subpath)
- NA Other configuration

# HTTPS
- handle by cert-manager and traefik

# Database
- postgresql

# Security hardening
- / Disable registration and (optionally) invitations
- / Disable password hint display
- NA Strict SNI (covered by reverse proxy, IP tracking is not possible)
- / Reverse proxying
- XPC Run as a non-root user
- XPC Mounting data into the container
- / Brute-force mitigation
- / Hiding under a subdir
- XPC Mounting data into the container


# Backup
- XPC Configuration
- XPC Database
