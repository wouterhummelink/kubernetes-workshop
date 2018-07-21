## Workshop

### Basics
Draai een shell in een pod

`kubectl run -i -t busybox --image=busybox --restart=Never`

### Deployments and services
Draai een webserver 

`kubectl run nginx --image=nginx --replicas=3 --port=80`

Scale it down/up

`kubectl scale deploy/nginx --replicas=1`
`kubectl scale deploy/nginx --replicas=5`

Expose the service as a Nodeport

`kubectl edit svc/nginx`

Vraag documentatie van de API

`kubectl explain svc.spec`

Toevoegen onder spec.ports nodePort: 30180
Set spec.type to NodePort

`kubectl describe svc/nginx`

### Secrets

`kubectl create secret generic mysql-secret --from-literal=mysql-root-password=devops`

### Persistent Volume

Maak een aantal persistentvolumes

`kubectl create -f pv00001.yml`
`kubectl create -f pv00002.yml`
`kubectl create -f pv00003.yml`

Maak een persistentvolumeclaim

`kubectl create -f mariadb-pvc.yml`
`kubectl get pvc`

Maak een pod met persistent storage

`kubectl create -f mariadb-pod.yml`
`kubectl describe pod/mariadb`


