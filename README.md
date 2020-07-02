# redis-cluster-with-opertor
This chart includes redis-cluster with dependent chart "redis-operator"

## Helm install

```console
  sachin@LAPTOP-0UP775BD ~/Redis-catalog/redis-cluster_withDep $ helm install redis-cl .
NAME: redis-cl
LAST DEPLOYED: Thu Jul  2 13:57:38 2020
NAMESPACE: default
STATUS: deployed
REVISION: 1
TEST SUITE: None
```

## To check helm depedency

```console
helm dep list
```

## To update the helm dependency

```console
helm dep build
  or
helm dep update
```

## Example
```
sachin@LAPTOP-0UP775BD ~/Redis-catalog/redis-cluster_withDep $ helm install redis-cl .
NAME: redis-cl
LAST DEPLOYED: Thu Jul  2 13:57:38 2020
NAMESPACE: default
STATUS: deployed
REVISION: 1
TEST SUITE: None

sachin@LAPTOP-0UP775BD ~/Redis-catalog/redis-cluster_withDep $ kubectl  get po
NAME                               READY   STATUS    RESTARTS   AGE
redis-operator-5d97bf558b-kz4br    1/1     Running   0          6m26s
rediscluster-redis-cl-24ltt        1/1     Running   0          6m22s
rediscluster-redis-cl-7wm2n        1/1     Running   0          5m38s
rediscluster-redis-cl-h4ntv        1/1     Running   0          5m56s

Deployed 2nd cluster:
sachin@LAPTOP-0UP775BD ~/Redis-catalog/redis-cluster_withDep $ helm install redis-cluster .
NAME: redis-cluster
LAST DEPLOYED: Thu Jul  2 14:03:52 2020
NAMESPACE: default
STATUS: deployed
REVISION: 1
TEST SUITE: None

sachin@LAPTOP-0UP775BD ~/Redis-catalog/redis-cluster_withDep $ kubectl  get po
NAME                               READY   STATUS    RESTARTS   AGE
redis-operator-5d97bf558b-kz4br    1/1     Running   0          9m30s
rediscluster-redis-cl-24ltt        1/1     Running   0          9m26s
rediscluster-redis-cl-7wm2n        1/1     Running   0          8m42s
rediscluster-redis-cl-h4ntv        1/1     Running   0          9m
rediscluster-redis-cluster-9wt5s   1/1     Running   0          3m16s
rediscluster-redis-cluster-pvn2n   1/1     Running   0          2m56s
rediscluster-redis-cluster-xrcl2   1/1     Running   0          2m39s
```
