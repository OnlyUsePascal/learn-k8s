NAMESPACE=my-namespace

ns-del:
	@kubectl delete namespace $(NAMESPACE)

ns-make:
	@kubectl create namespace $(NAMESPACE)

# small pod
# goal: to retrieve current date and exit
pod-make:
	@kubectl apply -n $(NAMESPACE) -f job-pod.yaml

pod-get:
	@kubectl get pod -n $(NAMESPACE)

pod-del:
	@kubectl delete pod -n $(NAMESPACE) -l app=my-app

# run pod using job
job-make:
	@kubectl apply -n $(NAMESPACE) -f job.yaml

job-get:
	@kubectl get job -n $(NAMESPACE) 

job-del:
	@kubectl delete job -n $(NAMESPACE) -l app=my-app

# run pod using cron job
job-cron-make:
	@kubectl -n $(NAMESPACE) apply -f job-cron.yaml

job-cron-manual:
	@kubectl -n $(NAMESPACE) create job --from=cronjob/my-cron-job my-cron-job-manual

job-cron-get:
	@kubectl -n $(NAMESPACE) get cronjob  

job-cron-del:
	@kubectl -n $(NAMESPACE) delete cronjob -l app=my-app


