# Golang-MicroServices

Nesse repositório possuem 5 microservices (catalog, checkout, order, payment, product), atendendo contextos diferentes, todos desenvolvidos em Golang.

## Tecnologias empregadas
- Kubernetes
- Golang
- Docker
- Istio
- Kiali
- Rabbitmq
- redis

## Subindo os serviços
- Instalando o Kubernetes (AKS ou EKS)
- Instale o istioctl
- Clone esse repositorio
- Execute:
   - kubectl apply -f ./k8s/ -R (Rodando recursivamente para aplicar todos os yaml)
   - istioctl install --set profile=demo -y
   - kubectl label namespace default istio-injection=enabled
   - kubectl delete --all pods --namespace=default (Recriando os pods com as políticas do Istio)
- Instalar o kiali dentro do cluster

## Pods em Execução:

```
NAME                           READY   STATUS    RESTARTS   AGE
catalog-566bb5c466-fdt4r       1/1     Running   0          13m
checkout-786f84fc74-md2kh      1/1     Running   0          13m
order-566c9ffbfd-hwj24         1/1     Running   0          13m
orderpayment-667cc6fbd-28w5w   1/1     Running   0          13m
payment-7f7b7c957d-kqls2       1/1     Running   0          13m
product-5d46f5d5d6-x69ls       1/1     Running   0          13m
rabbitmq-7fc9ddf955-q8zvl      1/1     Running   0          13m
redis-fd794cd65-vcgdj          1/1     Running   0          13m
```

## License
[MIT](https://choosealicense.com/licenses/mit/)