- replication controller make sure specified number of pods are running at all time.
- handles load balancing and scaling
- replication controller span across multiple pods.

Defining Replication Controller

```yaml
apiVersion: v1
kind: ReplicationController
metadata:
	name: myapp-rc
	lables:
		app: myapp
		type: frontend
spec:
	template:
		# define pods inside template
		metadata:
			name:
			labels:
				app: myapp
				type: front-end
		spec:
			containers:
				- name: nginx-container
				  image: nginx

	replicas: 3 # number of desired replicas
```

Defining ReplicaSet

Replicaset can manage pod created before defiining replicasets, they can be mentioned in the replicaset in Selector.

```yaml
apiVersion: apps/v1
kind: ReplicaSet
metadata:
	name: myapp-replicaset
	labels:
		app: myapp
		type: fullstack
spec:
	template:
		metadata:
			name: myapp-pod
			labels:
				app: myapp
				type: frontend
		spec:
			containers:
			- name: nginx-container
			  image: nginx
	replicas: 3
	selector: # not a required field
		matchLabels:
			type: frontend
```


```bash
kubectcl create -f <replicaset-definition.yml>

# list all replicaset
kubectl get replicaset

# delete replicaset
kubectl delete replicaset <replicaset-name>

# replcase replicaset set with updated replicas[scaling] or other definition changes
kubectl replace -f <replcaset-definition.yml>

# scale replicas on the fly, This does not update the original yaml
kubectl scale --replicas=<replicas_num> -f <replicaset-defintion.yml>
```

