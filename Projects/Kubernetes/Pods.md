
# PODS with YAML

pods definition template

```yaml
# this 4 fields are required fields and root level fields
apiVersion:
kind:
metadata:

spec:
```

| Kind       | Version |
| ---------- | ------- |
| Pod        | v1      |
| Service    | v1      |
| ReplicaSet | apps/v1 |
| Deployment | apps/v1 |

```yaml
apiVersion:
kind:
metadata:
	# kubernetes only support name and lables field inside metadata
	name:
	labels:
		# inside lables anyfield can be declared.
		app: myapp
		type: front-end
spec:
	containers:
		- name: nginx-container
		  image: nginx
```

```bash
# create pods
kubectl create -f {yaml_file_name}

# view pods
kubectl get pods

kubectl get pods pods --namespace=<namespace>

kubectl get pods --all-namespaces

# view details of a pod
kubectl describe pod {pod_name}
```


```bash
# export pod defintion to yaml
kubectl get pod <pod-name> -o yaml > <export-file-name.yaml>

# modify properties of a pod
kubectl edit pod <pod-name>

%% properties listed below are editable. 
- spec.containers[*].image
    
- spec.initContainers[*].image
    
- spec.activeDeadlineSeconds
    
- spec.tolerations
    
- spec.terminationGracePeriodSecond %%
```


```bash
# get pods with additional details
kubectl get pods -o wide
```








