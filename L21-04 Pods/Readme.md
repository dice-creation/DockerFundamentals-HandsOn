# L21-04

Let’s first create a node running Nginx by using the imperative way.

## Create the pod

    kubectl run mynginx --image=nginx

## Get a list of running pods

    kubectl get pods

## Get more info

    kubectl get pods -o wide
    kubectl describe pod mynginx

## Delete the pod

    kubectl delete pod mynginx

## Create a pod running BusyBox

Let’s now create a node running BusyBox, this time attaching bash to our terminal.

    kubectl run mybox --image=busybox -it -- /bin/sh

## List the folders and use command

    ls
    echo -n 'A Secret' | base64
    exit

## Cleanup
    
    kubectl delete pod mybox 
    kubectl delete pod mybox --wait=false
    kubectl delete pod mybox --grace-period=0 --force

## Create a pod using the declarative way

Let’s now create a node using a YAML file.

    kubectl create -f myapp.yaml

## Get some info

    kubectl get pods -o wide
    kubectl describe pod myapp-pod

## Attach our terminal

    kubectl exec -it myapp-pod -- bash

Print the DBCON environment variable that was set in the YAML file.

    echo $DBCON

## Detach from the instance

    exit

## Cleanup

    kubectl delete -f myapp.yaml


## Create a pod

    kubectl create -f [file.yaml]

## Run a pod

    kubectl run [podname] --image=busybox -- /bin/sh -c "sleep 3600"

## List the running pods

    kubectl get pods
    kubectl get pods -o wide

## Show pod inifo

    kubectl describe pod [podname]

## Extract the pod definition in YAML and save it to a file

    kubectl get pod [podname] -o yaml > file.yaml

## Interactive mode

    kubectl exec -it [podname] -- sh

## Delete a pod

    kubectl delete -f [file.yaml]

## Same using the pod name on delete a pod
    kubectl delete pod [podname]