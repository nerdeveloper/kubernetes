# External DNS

Project page: https://github.com/kubernetes-incubator/external-dns

## Create IAM Policy

```bash
./put-node-policy.sh
```

## start ingress

```bash
kubectl apply -f ../ingress/
```

## Create LoadBalancer for Ingress

```bash
kubectl apply -f service-l4.yaml
```

## Create external DNS and ingress rules

```bash
kubectl apply -f external-dns.yaml
kubectl apply -f ingress.yaml
```
