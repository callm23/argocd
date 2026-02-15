helm repo add tailscale https://pkgs.tailscale.com/helmcharts
helm repo update
helm upgrade \
  --install \
  tailscale-operator \
  tailscale/tailscale-operator \
  --namespace=tailscale \
  --create-namespace \
  --set-string oauth.clientId="<OAauth client ID>" \
  --set-string oauth.clientSecret="<OAuth client secret>" \
  --wait

1. Use Sidecar
Running as a sidecar lets you directly expose a Kubernetes pod over Tailscale. 


## Installation
Source: https://tailscale.com/docs/features/kubernetes-operator#setting-up-the-kubernetes-operator

1. Create OAuth client credentials needed by the operator to manage devices
--> check gitops or Terraform options for that