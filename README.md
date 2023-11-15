# Installation

Install UP CLI
```
curl -sL "https://cli.upbound.io" | sh
sudo mv up /usr/local/bin/
```
Install Upbound Universal Crossplane (UXP)

```

up uxp install
```

This will install all the necessary CRD's in the cluster + start the two controllers, the crossplane controller and the crossplane rbac controller too.

```
NAME                                             READY   STATUS    RESTARTS   AGE
crossplane-69c4cd787b-bcnwk                      1/1     Running   0          6m52s
crossplane-rbac-manager-76d9f95ff6-r5sxn         1/1     Running   0          6m52s
```
The crossplane pod is responsible for the CRD `Providers`.
The crossplane rbac pod is responsible for creating and dynamically adjust Kubernetes RBAC for all crossplane resources.

Then we can install the necessary provider for scaleway:

```
kubectl apply -f provider.yaml
```

You now have a pod to handle the scaleway provider and you can check the status of your provider like this :
`kubectl get providers`


