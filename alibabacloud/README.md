## Alibaba Cloud

## 环境准备
1. 一个ACK集群
1. 一个ASM实例，并开启了kiali功能
1. 将上面的ACK集群加入ASM实例，
1. ACK集群上部署ASM网关
## Quickstart
1. 将ACK集群namespace配置自动注入sidecar，默认用default
1. 部署原有的微服务，并增加productcatalogservice的v2版本
```
kubectl --kubeconfg <ack-config> apply -k ./v1
kubectl --kubeconfg <ack-config> apply -k ./v2
```
1. 部署istio网络规则
```
kubectl --kubeconfig <asm-config> apply -k ./asm
```
