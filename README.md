## 순서
1. ingress-nginx controller 설치
2. argocd 설치



### 1. ingress-nginx
```
helm -n kube-system install ingress-nginx ingress-nginx/ 
```

### 2. argocd
```
k create ns argocd
helm -n argocd install argocd argo-cd/ 
```


### keycloak
```
kubectl create ns keycloak
helm -n keycloak install keycloak keycloak/
helm -n keycloak upgrade keycloak keycloak/
helm -n keycloak uninstall keycloak
```

### Datahub

```
kubectl create ns datahub

helm -n datahub install prerequisites prerequisites/
helm -n datahub upgrade prerequisites prerequisites/

helm -n datahub install datahub datahub/
helm -n datahub upgrade datahub datahub/
```