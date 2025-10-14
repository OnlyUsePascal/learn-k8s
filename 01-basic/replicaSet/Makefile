NAMESPACE=my-namespace

delete-ns:
	@kubectl delete namespace $(NAMESPACE)

create-ns:
	@kubectl create namespace $(NAMESPACE)

get-pod:
	@kubectl get pod -n $(NAMESPACE)

get-rs:
	@kubectl get rs -n $(NAMESPACE)

create-rs:
	@kubectl apply -n $(NAMESPACE) -f replicaSet.yaml

delete-rs-file:
	@kubectl delete -n $(NAMESPACE) -f replicaSet.yaml

delete-rs-object:
	@kubectl delete -n $(NAMESPACE) replicaSet replica-set




