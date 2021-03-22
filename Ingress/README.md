# KIND 클러스터에 Ingress Controller 설치해보자

## Install ingress NGINX controller

### [Use KIND extra port mapping](https://kind.sigs.k8s.io/docs/user/ingress/)

```
# delete the previous cluster
kind delete cluster --name k8s101

# create the new cluster with extra port mapping
kind create cluster --name k8s101 --config kind-config.yaml
```

### [ingress nginx annotations](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/)

## Apply ingress and connect nip.io to wordpress
```
# get my internal ip address
./getmyip.sh

# copy paste into ingress.yaml 
- host: blog.xxx.xxx.xxx.xxx.nip.io

# apply ingress
kubectl apply -f ingress.yaml
```

## Alternative solution

* Use different type of ingress controller
* Change /etc/hosts file to access cluster with domain name
* Run socat docker image to connect host port to nodeport
```
docker run -d --name kind-proxy-80 \
--publish 80:80 \
--link k8s101-control-plane:target \
alpine/socat \
tcp-listen:80,fork,reuseaddr tcp-connect:target:32080
```
