# Jmeter Testing

- ENV
> Threading: 10000
> Prepare time: 10s
> Looping: 10

- Copy Test Case to Client
```
kubectl cp /home/ubuntu/Proxy-Compare-base.jmx ubuntu-8d695c7b4-l6tpv:/ -n proxy-compare
kubectl cp /home/ubuntu/Proxy-Compare-istio.jmx ubuntu-8d695c7b4-l6tpv:/ -n proxy-compare
kubectl cp /home/ubuntu/Proxy-Compare-linkerd.jmx ubuntu-8d695c7b4-l6tpv:/ -n proxy-compare
```

- Client Test Command
```
kubectl exec -ti ubuntu-8d695c7b4-l6tpv -n proxy-compare -- bash
jmeter -n -t Proxy-Compare-base.jmx -l Proxy-Compare-base.jtl
jmeter -n -t Proxy-Compare-istio.jmx -l Proxy-Compare-istio.jtl
jmeter -n -t Proxy-Compare-linkerd.jmx -l Proxy-Compare-linkerd.jtl
```

- Copy Result From Client 
```
kubectl cp ubuntu-8d695c7b4-l6tpv:/Proxy-Compare-base.jtl /home/ubuntu/Proxy-Compare-base.jtl -n proxy-compare
kubectl cp ubuntu-8d695c7b4-l6tpv:/Proxy-Compare-istio.jtl /home/ubuntu/Proxy-Compare-istio.jtl -n proxy-compare
kubectl cp ubuntu-8d695c7b4-l6tpv:/Proxy-Compare-linkerd.jtl /home/ubuntu/Proxy-Compare-linkerd.jtl -n proxy-compare
```
