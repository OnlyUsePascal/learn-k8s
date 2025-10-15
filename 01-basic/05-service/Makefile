NAMESPACE=my-namespace

ns-del:
	@kubectl delete namespace $(NAMESPACE)

ns-create:
	@kubectl create namespace $(NAMESPACE)

pod-get:
	@watch kubectl get pod -n $(NAMESPACE)

# deploy
depl-create:
	@kubectl apply -n $(NAMESPACE) -f deployment.yaml

depl-get:
	@kubectl get deployment -n $(NAMESPACE)

depl-desc:
	@kubectl describe deployment my-deployment -n $(NAMESPACE)

# service
svc-get:
	@kubectl get svc -n $(NAMESPACE) 

svc-del:
	@kubectl delete svc -n $(NAMESPACE) -l app=my-pod

svc-ip-create:
	@kubectl apply -n $(NAMESPACE) -f service-cluster-ip.yaml

svc-nodeport-create:
	@kubectl apply -n $(NAMESPACE) -f service-nodeport.yaml

svc-lb-create:
	@kubectl apply -n $(NAMESPACE) -f service-lb.yaml

# if using minikube
svc-nodeport-expose:
	@minikube service my-service-nodeport -n $(NAMESPACE) --url

svc-lb-expose:
	@minikube service my-service-lb -n $(NAMESPACE) --url

# curl pod for testing
curl-pod-same-cluster-create:
	@kubectl run -n $(NAMESPACE) curl-pod --image=curlimages/curl --command -- sh 
# @curl my-service-cluster-ip:80

curl-pod-diff-cluster-create:
	@kubectl run -n default curl-pod --image=curlimages/curl -it --command -- sh
# add namespace as parent domain
# @curl my-service-cluster-ip.$(NAMESPACE):80

curl-pod-del:
	@kubectl delete pod curl-pod -n $(NAMESPACE) 


