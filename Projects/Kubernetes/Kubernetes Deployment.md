```yaml
apiVersion: apps/v1
kind: Deployment
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

With Deployments you can easily edit any field/property of the POD template. Since the pod template is a child of the deployment specification,  with every change the deployment will automatically delete and create a new pod with the new changes. So if you are asked to edit a property of a POD part of a deployment you may do that simply by running the command

```bash
kubectl edit deployment my-deployment
```
