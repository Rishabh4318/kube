#Deploy
kubectl apply -f nginx-with-sidecar.yaml
#check pod is up and running
kubectl get pods
#generate some traffic
kubectl get pod nginx-with-sidecar -o wide
kubectl exec -it nginx-with-sidecar -c nginx -- curl localhost
Do this a few times — each request should generate an entry in access.log.

kubectl logs nginx-with-sidecar -c log-shipper