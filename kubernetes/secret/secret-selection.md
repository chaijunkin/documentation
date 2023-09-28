# Personal Opinion
- Kubernetes plain secret Object is secure
- Based on my usage (homelab + self-hosting), external secret operator (ESO) is more suitable for my use case. Since I'm using a lot of external helm chart that created by community, some helm chart template doesn't provide external Volume capability on the workload Deployment/Daemonset/Pod. As a result, using CSI volume for secret that mount secret as volume can be hassle for me because I refuse to maintain and modify the external chart. Therefore, I'm decided to explore on ESO because it can still using Secret as an Object which maintained by the operator.


# Reference:
- https://www.macchaffee.com/blog/2022/k8s-secrets/
- https://mixi-developers.mixi.co.jp/compare-eso-with-secret-csi-402bf37f20bc#:~:text=%22app%2Dsecrets%22-,Differences%20from%20ExternalSecret,and%20be%20the%20Secret%20resource.