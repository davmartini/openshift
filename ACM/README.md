# ACM notes

## Install submariner add-on

1. Label worker nodes

````
oc label node cluster01-dm-ocp-worker-0 submariner.io/gateway=true
oc label node cluster01-dm-ocp-worker-1 submariner.io/gateway=true
oc label node cluster01-dm-ocp-worker-2 submariner.io/gateway=true

oc label node cluster02-dm-ocp-worker-0 submariner.io/gateway=true
oc label node cluster02-dm-ocp-worker-1 submariner.io/gateway=true
oc label node cluster02-dm-ocp-worker-2 submariner.io/gateway=true
```