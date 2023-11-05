## kubernetes bootstrap

- Step 1: Deploy as usual

- Step 2: Remote inside
kubectl -n home-automation exec -it statefulset.apps/home-assistant -- bash

- Step 3: Put config in configuration.yaml
vi configuration.yaml

- Step 4: Exit container
exit

- Step 5: Delete container
kubectl delete pod/home-assistant-0 -n home-automation

- Step 6: Troubleshoot
kubectl -n home-automation logs statefulset.apps/home-assistant

Others:
