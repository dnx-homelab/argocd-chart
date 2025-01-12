# argocd-chart
- All argocd values
https://github.com/argoproj/argo-helm/blob/main/charts/argo-cd/values.yaml

- App of apps pattern
https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/#app-of-apps

- To check: https://argo-cd.readthedocs.io/en/stable/user-guide/application-set/

- Add repo
helm repo add argo-cd https://argoproj.github.io/argo-helm
- Create Chart.lock file
helm dep update charts/argocd
- Create namespace
kubectl create namespace argocd
- Install custom chart
helm install argocd -n argocd charts/argocd/
- Access web UI
kubectl port-forward svc/argocd-server -n argocd 8080:443
- Fix "server.secretkey is missing"
kubectl rollout restart deploy/argocd-server -n argocd


## root-app
- First time apply manually
helm template root-app/ | kubectl apply -f -

## Links
- https://www.arthurkoziel.com/setting-up-argocd-with-helm/
