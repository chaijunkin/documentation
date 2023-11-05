eval $(ssh-agent -s)
ssh-add ~/.ssh/<key_name>

git add -A .
git commit -m 'try navidrome to test pvc'
git push
flux reconcile kustomization cluster-apps --with-source
flux get ks -A