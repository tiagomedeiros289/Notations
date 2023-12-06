# Provisioners


Retorna o nome do provisioner junto com o instance-type
```
kubectl get provisioners -o custom-columns="NAME:.metadata.name,INSTANCE_TYPE:.spec.requirements[?(@.key=='node.kubernetes.io/instance-type')].values"

```