# Manual refresh secret
kubectl annotate es changedetection-volsync force-sync=$(date +%s) --overwrite