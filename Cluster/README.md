# k8s cluster 설치

## ctlptl(coddle poodle - 커들푸들)
[ctlptl github](https://github.com/tilt-dev/ctlptl)
```
brew install tilt-dev/tap/ctlptl
```

built-in registry on KIND cluster
```
❯ ctlptl create cluster kind --registry=ctlptl-registry

Creating registry "ctlptl-registry"...
Creating cluster "kind" ...
 ✓ Ensuring node image (kindest/node:v1.21.1) 🖼
 ✓ Preparing nodes 📦
 ✓ Writing configuration 📜
 ✓ Starting control-plane 🕹️
 ✓ Installing CNI 🔌
 ✓ Installing StorageClass 💾
Set kubectl context to "kind-kind"
You can now use your cluster with:

kubectl cluster-info --context kind-kind

Have a nice day! 👋
   Connecting kind to registry ctlptl-registry
Switched to context "kind-kind".
 🔌 Connected cluster kind-kind to registry ctlptl-registry at localhost:59163
 👐 Push images to the cluster like 'docker push localhost:59163/alpine'
cluster.ctlptl.dev/kind-kind created
```
kubeconfig 은 ~/.kube/config 에 kind-kind context 로 저장이 된다.
## KIND


[KIND 설치](https://kind.sigs.k8s.io/docs/user/quick-start/#installation)
(도커가 미리 설치 되어 있어야 합니다)

```
brew install kind
```
KIND 로 클러스터를 만들어 봅시다.
```
kind create cluster --name k8s101-kind --config kind-config.yaml
```

[Collection of toolz](https://github.com/tomhuang12/awesome-k8s-resources?fbclid=IwAR2lulAEgAXqwjm0GHzBhDSEzkLAA2X0rrqBpIfLAV3TM0mdO98IjDLjMo8)