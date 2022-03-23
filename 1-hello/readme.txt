patchesStrategicMerge


kubectl kustomize overlays/one

kubectl kustomize overlays/one > tmp.yaml

And then compare to the base/deployment.yaml to check the overrides

Note the -k vs -f

kubectl apply -k overlays/one

kubectl describe deployment myapp 

Looking for the correct image override

kubectl exec -it $(kubectl get pod -l app=myapp -o name) -- /bin/bash

curl localhost:8080

Bonjour from Spring Boot!

# note it can take many seconds for the Java-based Spring Boot to come up

kubectl delete -k overlays/one


kubectl apply -k overlays/two

there should be 3 replicas

kubectl delete -k overlays/two

Three is injecting a resources requests & limits sections

kubectl apply -k overlays/three

kubectl describe deployment myapp 

looking for the correct resource overrides

kubectl delete -k overlays/three


kubectl apply -k overlays/four


kubectl exec -it $(kubectl get pod -l app=myapp -o name) -- /bin/bash
echo $GREETING

curl localhost:8080
Namaste from Spring Boot!

kubectl delete -k overlays/four
