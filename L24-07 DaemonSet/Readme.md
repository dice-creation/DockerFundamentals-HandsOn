# L24-07
Let's deploy a Busybox as a DaemonSet.
detail and usecase:
- Ensures all nodes run an instance of a Pod
- Scheduled by the scheduler controller and run by the daemon controller
-as nodes are added to the cluster, Pods are added to them
-Typical uses
  Running a cluster storage daemon
  Running a log collection daemon on every node
  Running a node monitoring daemon on every node

## Create the Deployment

    kubectl apply -f daemonset.yaml

## List DaemonSets

    kubectl get ds

## Get info

    kubectl describe ds [rsName]

## Get the pods list

There should be one for each worker node.

    kubectl get pods --selector=app=daemonset-example -o wide

## Cleanup

    kubectl delete -f daemonset.yaml