# Github action to use AWS secrets and wrap them to create
* JSON file
* Values for Helm charts (yml, yaml)
* export to file to create to github runner environment



# The input variables are:

* the path of the secret is like this:
   PROJECT/APP/SERVICE/INSTANCE/VERSION

for instance we use the branch: e.g. development/staging/production
and for the VERSION it can be: build_vars, kubernetes_vars, running_vars etc.

```
  PROJECT:
    required: true
  APP:
    required: true
  SERVICE:
    required: true
  INSTANCE:
    required: true
  VERSION:
    required: true
```

* the credentials to use to access the secrets:

```
  AWS_ACCESS:
    required: true
  AWS_SECRET:
    required: true
  AWS_ZONE:
    required: false
    default:  "us-east-1"
```

* the file to export in yaml format for chart environment:
similar to this:
```
environment:
    key1: value1
    key2: value2
```

```    
  SECRETSJSON_2_HELMFILE:
    required: false
    default: "false"
```
* the file to export in GITHUB_ENV

```
  SECRETSJSON_2_GITENV:
    required: false
    default: "false"
```

* JSON output to file

```    
  SECRETSJSON_2_FILE:
    required: false
    default: "false"
```    
