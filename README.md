# argocd

## Login

```bash
argocd login 192.168.1.241:31670 --insecure --username admin
```

## Prometheus from Helm chart

```bash
argocd app create prometheus --repo https://prometheus-community.github.io/helm-charts --helm-chart prometheus --revision 25.8.0 --dest-namespace monitoring --dest-server https://kubernetes.default.svc --sync-policy automated --values values.yaml
```

## Git repo

```bash
argocd app create infrastructure --repo https://github.com/callm23/argocd.git --path infrastructure --dest-namespace infrastructure --dest-server https://kubernetes.default.svc --sync-policy automated
```

## Prometheus node exporter

```bash
argocd app create prometheus-node-exporter --repo https://prometheus-community.github.io/helm-charts --helm-chart prometheus-node-exporter --revision 4.46.1 --dest-namespace monitoring --dest-server https://kubernetes.default.svc --sync-policy automated --values values.yaml
```

## Prometheus metrics server

```bash
argocd app create metrics-server --repo https://kubernetes-sigs.github.io/metrics-server/ --helm-chart metrics-server --revision 3.12.2 --dest-namespace monitoring --dest-server https://kubernetes.default.svc --sync-policy automated --values values.yaml
```

## Paperless-ngx

```bash
argocd app create paperless-ngx --repo oci://codeberg.org/wrenix/helm-charts/paperless-ngx --revision 0.2.1 --dest-namespace paperless-ngx --dest-server https://kubernetes.default.svc --sync-policy automated --values values.yaml
```

  argocd app create helm-guestbook --repo https://github.com/argoproj/argocd-example-apps.git --path helm-guestbook --dest-namespace default --dest-server https://kubernetes.default.svc --helm-set replicaCount=2

  # Create a Helm app from a Helm repo
  argocd app create nginx-ingress --repo https://charts.helm.sh/stable --helm-chart nginx-ingress --revision 1.24.3 --dest-namespace default --dest-server https://kubernetes.default.svc

## OpenBao

Init repo
kubectl exec -ti openbao-0 -- bao operator init

argocd app create eso --repo https://github.com/callm23/argocd.git --path applications\eso\external-secrets\templates --dest-namespace eso --dest-server https://kubernetes.default.svc --sync-policy automated

C:\work\git\argocd\argocd\