kubectl create -f glusterfs.yaml
kubectl create -f heketi.yaml
kubectl create clusterrolebinding heketi-gluster-admin --clusterrole=edit --serviceaccount=default:heketi-service-account

kubectl exec -it "heketi-xxxx" /bin/bash
cd /etc/heketi
add file topology.json

export HEKETI_CLI_SERVER=http://localhost:8080
heketi-cli -s $HEKETI_CLI_SERVER --user admin --secret "My Secret" topology load --json=topology.json
heketi-cli topology info --user admin --secret "My Secret"
