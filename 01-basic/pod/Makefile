NAMESPACE=my-namespace

delete-ns:
	@kubectl delete namespace $(NAMESPACE)

create-ns:
	@kubectl create namespace $(NAMESPACE)

get-pod:
	@kubectl get pod -n $(NAMESPACE)

create-pod-cmd:
	@kubectl run --image=nginx:1.26.0 -n $(NAMESPACE) pod-cmd

create-pod-minimal:
	@kubectl apply -n $(NAMESPACE) -f pod-minimal.yaml

forward-pod-minimal:
	@kubectl port-forward -n $(NAMESPACE) pod-minimal 8080:80

create-pod-detail:
	@kubectl apply -f pod-detail.yaml

forward-pod-detail:
	@kubectl port-forward -n $(NAMESPACE) pod-detail 8080:8080






