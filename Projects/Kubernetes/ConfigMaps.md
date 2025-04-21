
Creating ConfigMaps

Imperative way-
```bash
kubectl create configmap
		<config-name> --from-literal=<key>=<value>
```

```bash
kubectl create configmap
		<config-name> --from-file=<path-to-file>
```

Declarative way

```yaml
apiVersion: v1
kind: ConfigMap
metadata:
	name: <name>
data:
	<key>: <value>
	<key>: <value>
```

Using ConfigMaps

as Env:

```yaml
apiVersion: v1
kind: Pod
metadata:
	name: <name>
	labels:
		name: <name>
spec:
	containers:
		- name: <container-name>
		  image: <container-image>
		  ports:
			  - containerPort: 8080
		  envFrom:
			  - configMapRef:
				  - name: <config-map-name>
```


as Single Env:
```yaml
env:
	- name: <name>
	  valueFrom:
		  configMapKeyRef:
			  name: <config-map-name>
			  key: <key>
```

as Volume:

```yaml
volumes:
  - name: <volume-name>
	configMap:
		name: <config-map-name>
```

