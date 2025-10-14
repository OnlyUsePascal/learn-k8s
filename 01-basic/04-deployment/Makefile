NAMESPACE=my-namespace

delete-ns:
	@kubectl delete namespace $(NAMESPACE)

create-ns:
	@kubectl create namespace $(NAMESPACE)

get-pod:
	@watch kubectl get pod -n $(NAMESPACE)

get-dep:
	@kubectl get deployment -n $(NAMESPACE)

desc-dep:
	@kubectl describe deployment my-deployment -n $(NAMESPACE)

roll-stat:
	@kubectl rollout status -n $(NAMESPACE) deployment my-deployment

roll-hist:
	@kubectl rollout history -n $(NAMESPACE) deployment my-deployment
	
roll-undo:
	@kubectl rollout undo -n $(NAMESPACE) deployment my-deployment

roll-v1:
	@kubectl apply -n $(NAMESPACE) -f deployment-v1.yaml

roll-v2:
	@kubectl apply -n $(NAMESPACE) -f deployment-v2.yaml

# fail
roll-v3:
	@kubectl apply -n $(NAMESPACE) -f deployment-v3.yaml


