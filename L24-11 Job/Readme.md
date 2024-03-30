# L24-11

Let's now use the Job template.
-Workload for short lived tasks
-Creates one or more Pods and ensures that a specified number of them successfully termnate
-As pods successfully complete, the Job tracks the successfu completions
-When a specified number of successful completions is reached, the Job completes
-on Configure job.yaml always set "restartPolicy to Never"

## Create the Job

    kubectl apply -f job.yaml

## Get the jobs list

    kubectl get jobs

## Get more info

    kubectl describe job

## Get the pod name

Get the pod's log.  Something starting with **hello-**

    kubectl get pods

## Get the jobs list

Get the container's log.  You should see **Hello from the Job**.

    kubectl logs <podName>

## Cleanup

    kubectl delete -f job.yaml