# demoapp (nginx)
```
Can be deployed using Argo CD or directly.
```
#### How to deploy Argo CD?
```
kind create cluster &&
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml
```
```
kubectl create ns argocd && kubens argocd && helm repo add argo https://argoproj.github.io/argo-helm && 
helm repo update && 
helm install my-release argo/argo-cd &&
cat ~/.ssh/id_ed25519 | base64 > myfile &&
kubectl create secret generic my-deploy-secret --from-file=privateKey=myfile
```
```
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
kubectl port-forward service/my-release-argocd-server -n argocd 8080:443
```


```
Fecthing argocd helm chart using:
helm pull argo/argo-cd --untar

kubectl create ns argocd && kubens argocd && helm install -f argocd-chart/values.yaml my-argocd-test ./argocd-chart

```


#### How to configure Argo CD?
```
Login to the ArgoCD UI and create a application manually (OR apply argocd-app.yaml) 

Now You can access demo app deployed by argocd locally using:
kubectl port-forward service/nginx-service 9090:80
http://127.0.0.1:9090/

kubectl port-forward svc/argo-cd-argocd-server 8080:443
kubectl port-forward svc/nginx-svc 8080:80
kubectl port-forward svc/nginxplain-svc 8080:80
kubectl port-forward svc/springpet-svc 8080:8081

http://127.0.0.1:8080

```
