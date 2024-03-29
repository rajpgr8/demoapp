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
Fecthing argocd helm chart using:
helm pull argo/argo-cd --untar

kubectl create ns argocd && kubens argocd && helm install -f argocd-chart/values.yaml my-argocd-test ./argocd-chart

```

#### How to configure Argo CD?
```
kubectl port-forward svc/argo-cd-argocd-server 8080:443
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d

Now login to the ArgoCD UI and create a root application manually (OR apply file argocd_applications.yaml manually using kubctl) 
Argocd will deploy all the menifiest present in the defined path.

```

#### How to access deployed apps?
```
kubectl port-forward svc/springpet-svc  9090:9090
kubectl port-forward svc/echo           8080:8080
kubectl port-forward svc/nginx-svc      8081:8081
kubectl port-forward svc/nginxplain-svc 8082:8082

Then check:
 http::127.0.0.1:9090
 http::127.0.0.1:9090/actuator/health
 http::127.0.0.1:9090/actuator/prometheus
 http::127.0.0.1:8080
 http::127.0.0.1:8081
 http::127.0.0.1:8082
```
