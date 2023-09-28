## create kubernetes token
kubectl create serviceaccount admin-user
kubectl create clusterrolebinding admin-user-binding \
  --clusterrole cluster-admin \
  --serviceaccount default:admin-user

kubectl create token admin-user