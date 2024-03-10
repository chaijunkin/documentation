## kubernetes bootstrap

- Step 1: Deploy as usual

- Step 2: Remote inside
kubectl -n home-automation exec -it deployment.apps/home-assistant -- bash

- Step 3: Put config in configuration.yaml
vi /config/configuration.yaml

http:
  server_host: 0.0.0.0
  ip_ban_enabled: true
  login_attempts_threshold: 5
  trusted_proxies:
    - !env_var HASS_HTTP_TRUSTED_PROXY_1
    - !env_var HASS_HTTP_TRUSTED_PROXY_2
  use_x_forwarded_for: True

- Step 4: Exit container
exit

- Step 5: Scale up and scale down container replicas
1 --> 0 --> 1

- Step 6: Troubleshoot
kubectl -n home-automation logs statefulset.apps/home-assistant

Others:
