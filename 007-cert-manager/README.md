# cert-manager

**This installation is required only once per cluster.**

[ArtifactHub - cert-manager](https://artifacthub.io/packages/helm/cert-manager/cert-manager)

## Install and configure cert-manager

```shell
helm repo add jetstack https://charts.jetstack.io
```

```shell
helm repo update
```

```shell
kubectl create namespace cert-manager
```

```shell
helm upgrade --install cert-manager jetstack/cert-manager --namespace cert-manager --version v1.9.1 --set installCRDs=true
```

## Configuration for route53

* Add AWS cert-manager Secret Key to `credentials-secret.yaml` (base64 encoded!)
* Add AWS cert-manager Access Key to `clusterissuer.yaml`

* Create ClusterIssuer

  ```shell
  kubectl apply -f credentials-secret.yaml
  kubectl apply -f clusterissuer.yaml
  ```

* Create wildcard certificate

  ```shell
  kubectl apply -f certificate.yaml
  ```

* last step: activate the ingress-nginx default-ssl-certificate
in the previous hands-on folder in the file `values.yaml` and update ingress-nginx release
