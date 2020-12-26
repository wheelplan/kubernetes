```Bash
kubectl create -f glusterfs.yaml

kubectl create -f heketi.yaml

kubectl create -f heketi-config.yaml

kubectl create -f heketi-rbac.yaml

dd if=/dev/zero of=/dev/vdb bs=1M seek=10000 count=0

losetup /dev/loop0 /dev/vdb
```

```Bash
kubectl exec -it "heketi-xxxxx-xxxx" /bin/bash

export HEKETI_CLI_SERVER=http://localhost:8080

heketi-cli -s $HEKETI_CLI_SERVER --user admin --secret "My Secret" topology load --json=/tmp/topology.json

heketi-cli topology info --user admin --secret "My Secret"
```
