# HAProxy gRPC Load balancer

1. I used haproxy sit behind grpc server, the number of the back-end server should be equal to the max of grpc server replicas.

2. To test the configuration, update container image and image pull recret.

```shell
kubectl create secret generic regcred \
    --from-file=.dockerconfigjson=.dockerconfig.json \
    --type=kubernetes.io/dockerconfigjson -n haproxy
```

3. Test

```shell
kubectl create -f load-balancer.yaml
```
