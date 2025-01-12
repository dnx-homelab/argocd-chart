# argocd-chart
- All argocd values
https://github.com/argoproj/argo-helm/blob/main/charts/argo-cd/values.yaml

- Add repo
helm repo add argo-cd https://argoproj.github.io/argo-helm
- Create Chart.lock file
helm dep update charts/argocd

