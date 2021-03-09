# 워드프레스를 kind 클러스터에 배포해보자

Create namespace
``` 
kubectl create namespace wordpress
```
Set namespace
```
kubectl config set-context --current --namespace=wordpress
```

Create secret for mysql
```
cat <<EOF >./kustomization.yaml
secretGenerator:
- name: mysql-pass
  literals:
  - password=test123
generatorOptions:
  disableNameSuffixHash: true
EOF
```
Run kustomize to apply secret for mysql
```
kubectl -k ./
```
Add mysql and wordpress deployments in kustomization
```
cat <<EOF >>./kustomization.yaml
resources:
  - mysql-deployment.yaml
  - wordpress-deployment.yaml
EOF
```
Apply and verify
```
kubectl apply -k ./

# watch while pods status changes
kubectl get pods -w

# verify secret
kubectl get secrets

# verify pvc
kubectl get pvc
 
# verify pv
kubectl get pv

# verify svc status
kubectl get services

# verify k8s events
kubectl get events
```
Check availability

```
# check wordpress web
kubectl port-forward svc/wordpress 8080:80
# open browser with url: localhost:8080

# check mysql server
kubectl port-forward svc/wordpress-mysql 3306:3306

mycli -h localhost -p 3306 -u root -p test123
```

## To do

* Implement Ingress controller
* attach proxy for docker
* use nip.io to connect to wordpress

