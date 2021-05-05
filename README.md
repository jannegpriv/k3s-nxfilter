# k3s-nxfilter
Support for running NXFilter in K3s.

Yaml-files for:

* Creating the managed-nfs-storage-nxfilter storage class, deployment and rbac for the NFS client provisioner/xternal_storage that is used for creating PV based on NFS server
* Creating PVC using the managed-nfs-storage-nxfilter storage class
* Creating a deployment using an home bult NXFilter container
* Creating a K3s Service
* Creating a K3s Ingress controller based on Traefik 

Start with deploying the NFS client provisioner:
`k apply -f deploy/rbac.yaml -f deploy/class.yaml -f deploy/deployment-arm.yaml`

Then deploy the nxfilter:
`k apply -f openhab-claims.yaml -f openhab-service.yaml -f openhab-traefik.yaml -f openhab-deployment.yaml`
