# Personal Charts Repo
This is a simple charts repo, hosted directly in github. All the charts are
stored under `helm/charts`.

## Adding a new chart
First, regular chart creation and packaging process:

```
helm create <my-chart>
# some coding
helm package <my-chart>
mv <my-chart>-0.1.0.tgz helm/charts
```

Then, we need to reindex and push the changes:

```
helm repo index helm/charts --url https://boris.github.io/kubernetes/helm/charts/
git add .
git commit -m "reindex"
git push
```

## Adding the repo
Regular process:

```
helm repo add boris https://boris.github.io/kubernetes/helm/charts/
helm repo list
NAME                    URL
ealenn                  https://ealenn.github.io/charts
bitnami                 https://charts.bitnami.com/bitnami
kubernetes-dashboard    https://kubernetes.github.io/dashboard/
argo                    https://argoproj.github.io/argo-helm
boris                   https://boris.github.io/kubernetes/helm/charts/
```
