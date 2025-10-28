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

conf-get:
	@$(KBE) get configmap

conf-file-make:
	@$(KBE) apply -f config-file.yml

conf-property-make:
	@$(KBE) apply -f config-property.yml

conf-consumer-make:
	@$(KBE) apply -f config-consumer.yml

runner-consumer:
	@$(KBE) exec -it configmap-example -- bash
# cat /etc/config/conf.yml
# printenv
