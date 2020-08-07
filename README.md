Sample Deployment
=================

This deployment create pvc and index.html into pvc volume. 
So if pod name is displayed when you execute `curl localhost` into pod, your k8s cluster is ok for making Pods and PVCs.

## Howto

> Before apply, you should modify `storageClassName` for your environment.

```
$ kubectl apply -f web.yaml

$ kubectl exec -it $(kubectl get pods -l app=nginx --template '{{range .items}}{{.metadata.name}}{{"\n"}}{{end}}') curl localhost
web-8558dcd7dd-n9tlj

$ kubectl delete -f web.yaml
```

