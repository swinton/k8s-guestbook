# `k8s-guestbook`

An example guestbook running on Kubernetes, in two separate namespaces, `staging` and `production`, managed through kustomization layers.

## Prequisites

- Setup [Minikube](https://github.com/kubernetes/minikube).

## Setup

### Namespaces

```shell
kubectl apply -k ./k8s-config/namespaces
```

### Staging

```shell
kubectl apply -k ./k8s-config/staging
```

### Production

```shell
kubectl apply -k ./k8s-config/production
```

## Accessing the services

### Staging

```shell
minikube service frontend --namespace=staging --url
```

### Production

```shell
minikube service frontend --namespace=production --url
```

## Cleanup

### Staging

```shell
kubectl delete -k ./k8s-config/staging
```

### Production

```shell
kubectl delete -k ./k8s-config/production
```

## Resources

- [Example: Deploying PHP Guestbook application with Redis](https://kubernetes.io/docs/tutorials/stateless-application/guestbook/#cleaning-up)
- [Declarative Management of Kubernetes Objects Using Kustomize](https://kubernetes.io/docs/tasks/manage-kubernetes-objects/kustomization/)
