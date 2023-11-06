

Pegando o valor de uma label nos nodes que estão dentro de uma faixa de IPs.

```
# Do Ip 10.101.240 até 10.101.247
export IP_RANGE="10.101.24[0-7]"

# Nome da Label
export LABEL_NAME="provisioner-name"

for n in `kubectl get nodes | grep -E "$IP_RANGE" | awk '{print $1}'`; do kubectl get node $n -o yaml | grep "$LABEL_NAME" | awk '{print $2} '; done | sort | uniq
```