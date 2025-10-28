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

pod-del:
	@$(KBE) delete pod -l app=my-app

svc-get:
	@$(KBE) get service

# replica set
replica-make:
	@$(KBE) apply -f replica-set.yml

replica-get:
	@$(KBE) get replicaset

replica-del:
	@$(KBE) delete replicaset -l app=my-app

# daemon set
daemon-make:
	@$(KBE) apply -f daemon-set.yml

daemon-get:
	@$(KBE) get daemonset

daemon-del:
	@$(KBE) delete daemonset -l app=my-app

# stateful set
stateful-make:
	@$(KBE) apply -f stateful-set.yml

stateful-get:
	@$(KBE) get statefulset

stateful-del:
	@$(KBE) delete statefulset -l app=my-app

stateful-expose:
	@$(MKBE) service  --url

runner-dns:
	@$(KBE) run -it --image busybox:1.28 dns-pod --restart=Never --rm
# nslookup nginxs -> it will shows address of 3 pods

runner-curl:
	@$(KBE) run curl-pod --image=curlimages/curl -it --restart=Never --rm --command -- sh 
# curl nginx-with-init-conainer-0.nginxs.my-namespace.svc.cluster.local
# still have no idea why `nslookup nginxs` has different result from above

