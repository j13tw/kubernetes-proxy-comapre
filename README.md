# Kubernetes Service Mesh Proxy Container Compare

# Base
> Dir ```base```
> Place the no Proxy Container Injection Service

```
kubectl apply -f base/
```

## Istio
> Dir ```Istio``` Service Mesh with ```sidecar proxy```

```
kubectl apply -f istio/
```

## Linkerd
> Dir ```Linkerd``` Service Mesh with Rust lang base ```proxy```

```
kubectl apply -f linkerd/
```

## Benchmark Client
> Base on ```Ubuntu 20.04```
```
kubectl apply -f client
```
