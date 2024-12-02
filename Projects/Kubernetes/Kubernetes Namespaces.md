### Creating Namespace
```bash
kubectl create namespace <namespace>
```
or
```yaml
apiVersion: v1
kind: Namespace
metadata:
	name: <namespace>
```
```bash
kubectl get pods --namespace=<namespace>
```


creating pod in a specific namespace
```bash
kubectl create -f <pod-defintion.yml> --namespace=<namespace>
```
or, add it to pod definition
```yaml
apiVersion: v1
kind: Pods
metadata:
	name: myapp
	namespace: <namespace>
	labels:
		app: myapp
		type: front-end
spec:
	containers:
		- name: nginx-container
		  image: nginx
```

change default namespace
```bash
kubectl config set-context $(kubectl config current-context) --namespace=<namespace>
```

### ResourceQuota

```yaml
apiVersion: v1
kind: ResourceQuota
metadata:
	name: compute-quota
	namespace: dev
spec:
	hard:
		pods: "10"
		requests.cpu: "4"
		requests.memory: 5Gi
		limits.cpu: "10"
		limit.memory: 10Gi
```





