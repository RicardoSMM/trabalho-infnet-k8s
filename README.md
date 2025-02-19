# trabalho-infnet-k8s a

# Instalando o Longhorn
kubectl apply -f https://raw.githubusercontent.com/longhorn/longhorn/master/deploy/longhorn.yaml
# Expondo a porta da UI em nodePort 30080
kubectl -n longhorn-system expose deployment longhorn-ui --type=NodePort --overrides='{"spec": {"ports": [{"nodePort": 30080, "port": 8000, "target": 8000}]}}' --port=8000