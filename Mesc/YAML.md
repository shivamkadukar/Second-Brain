Valid file extensions `.yml` `.yaml`

> YAML is superset of JSON: any valid JSON file is also a valid YAML file

`# this is a comment`

```yaml
# this is an object
microservice:
	app: user-authentication
	port: 9000
	version: 1.7
```

```yaml
# this is how list are declared in yaml
microservice:
	- app: user-authentication
	  port: 9000
	  version: 1.7
	  deployed: true # booleans are supported
	- app: checkout-service
	  port: 8080
	  version: 1.6
	  # using environment variables with $
	  command: 
		- /bin/sh
		- -ec
		- >-
		   mysql -h 127.0.0.1 -u root -p $MYSQL_PASSWORD -e 'SELECT 1'
	  # this is an alternate way of defining lists
	  args: ["-c", "echo hellow= from checkout-service"]
	  # multi line string
	  comment: |
		  this is a how multi
		  line string are declared
		  in yaml.
	  # single line string but declared in multiple lines
	  comment_2: >
		  this is a single line string
		  that should be all on one line.
```

```yaml
# placeholders are defined inside {{}}
apiVersion: v1
kind: Service
metadata:
	name: {{ .Values.service.name }}
spec:
	selector:
		app: {{ .Values.service.app }}

# mutliple components can be defined in single yaml by separating them with ---
---
apiVersion: v1
kind: Service
metadata:
	name: {{ .Values.service.name }}
spec:
	selector:
		app: {{ .Values.service.app }}
```

```yaml
# list without key value pairs are supported
microservice:
	- user-authentication
	- checkout-service
```




