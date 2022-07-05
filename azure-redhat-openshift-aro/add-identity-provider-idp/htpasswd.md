---
description: How to add htpasswd identity provider
---

# htpasswd

1. Create **htpasswd** file using htpasswd command and add user(s)

```
# install htpasswd tool
# Ubuntu
sudo apt install apache2-utils

# create file and first user
htpasswd -c -B -b ./htpasswd student redhat123

# add user to exiting file
htpasswd -b ./htpasswd student2 redhat456
```

2\. Create **secret** resource in Openshift cluster

```
oc create secret generic htpasswd-secret \
 --from-file htpasswd=./htpasswd -n openshift-config
```

3\. Edit oauth/cluster to add HTPasswd type provider

```
oc edit oauth/cluster

# add new provider to list .spec.identityProviders
spec:
  identityProviders:
  - name: my_htpasswd_provider
    mappingMethod: claim
    type: HTPasswd
    htpasswd:
      fileData:
        name: htpasswd-secret
```

4\. Wait until all **openshift-oauth-\*** pods get recreated under **openshift-authentication** namespace

5\. Open Openshift login page again and you should see the new login option\
![](../../.gitbook/assets/image.png)
