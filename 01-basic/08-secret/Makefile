NAMESPACE=my-namespace
KBE=kubectl -n $(NAMESPACE)
MKBE=minikube -n $(NAMESPACE)

# some utils
ns-del:
	@kubectl delete namespace $(NAMESPACE)

ns-make:
	@kubectl create namespace $(NAMESPACE)

pod-get:
	@$(KBE) get pod 

svc-get:
	@$(KBE) get service

secret-get:
	@$(KBE) get secret

secret-opaque-make:
	@$(KBE) apply -f secret-opaque.yml

secret-opaque-get:
	@$(KBE) get secrets secret-opaque -o yaml | yq '.data'

secret-dockerconfig-make:
	@$(KBE) apply -f secret-dockerconfig.yml

secret-consumer-make:
	@$(KBE) apply -f secret-consumer.yml

secret-consumer-runner:
	@$(KBE) exec -it secret-example -- bash
# cat /etc/config/key1
# printenv
