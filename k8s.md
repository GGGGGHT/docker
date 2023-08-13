# kubernetes

## ingress/
ingress 是对集群中服务的外部访问进行管理的API对象, 典型的访问方式是通过HTTP, Ingress可以提供负载均衡等功能.

Ingress 公开从集群外部到集群内服务的 HTTP 和 HTTPS 路由。 流量路由由 Ingress 资源上定义的规则控制。
![image](https://github.com/GGGGGHT/docker/assets/26846402/8d0940c8-2643-484f-bdb0-d44ce0ef0ec7)

```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: minimal-ingress
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /
spec:
  ingressClassName: nginx-example
  rules:
  - http:
      paths:
      - path: /testpath
        pathType: Prefix
        backend:
          service:
            name: test
            port:
              number: 80

```


### ingress规则 


###　主机名通配符
