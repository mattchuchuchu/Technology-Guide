# Installation Steps

1. Install Linux Subsystem and select Ubuntu to install on Windows.
https://docs.microsoft.com/en-us/windows/wsl/install-win10

2. Install Windows Terminal
https://aka.ms/terminal

3. Install Azure CLI
https://docs.microsoft.com/en-us/cli/azure/install-azure-cli-apt?view=azure-cli-latest

4. Install kubectl
https://kubernetes.io/docs/tasks/tools/install-kubectl/

   Problems:
   - chmod +x ./kubectl cannot be executed due to limited access.
  Resolved with sudo chmod +x ./kubectl instead.
   - 

5. Connect aks
https://docs.microsoft.com/en-us/azure/aks/tutorial-kubernetes-deploy-cluster


# Prepare

1. *Login azure*<br/>
`az login`<br/>
`az login --allow-no-subscriptions`<br>
`az login --use-device-code`<br>

2. *Switch Subscription*<br/>
`az account set --subscription *subscription_name*`<br/>

3. *Connect*<br/>
`az aks get-credentials --subscription *subscription_id* -g vnet-resources -n devops-aks-apps`<br/>
`az aks get-credentials --subscription *subscription_id* -g vnet-resources -n devops-aks-apps`


# Commands

## useful commands
1. *Get all the running pods*<br/>
`kubectl get pod -n *ns_name*`<br/>
`kubectl delete pod *pod_name* -n *ns_name* `<br/>

2. *Check log in a pod*<br/>
`kubectl logs *pod_name* -n *ns_name*`<br/>

3. *Connect a pod to execute more commands*<br/>
`kubectl exec -it *pod_name* bash -n *ns_name*`<br/>
`kubectl exec -it *pod_name* -n lmsdemo -- bash`<br/>
`kubectl exec [POD] [COMMAND] is DEPRECATED and will be removed in a future version. Use kubectl exec [POD] -- [COMMAND] instead.`


`kubectl describe pod/*pod_name* -n *ns_name*`

4. *Get all the services*<br/>
`kubectl get svc -n *ns_name*`<br/>

5. *Access one service locally*<br/>
`kubectl port-forward service/bank 8000:16007 -n *ns_name*`<br/>

## kubectl commands

1. *getting kubectl cluster info to check if kubectl is configured properly*
`kubectl cluster-info`

`kubectl get pods --all-namespaces`



# Scenarios

## Retrieve logs from k8s to local

Step1 - zip log in pod
```
ssh user@host (remote linux)
kubectl get pod -n *ns_name*
kubectl logs *pod_name* -n *ns_name*
kubectl exec -it *pod_name* bash -n *ns_name*
tar -cvf logs.1119.tar logs
exit (go back to linux)
```
Step2 - download to linux from k8s
```
kubectl cp *pod_name*:logs.1119.tar ./logs/logs.1119.tar -n *ns_name*
##sz logs.learn_1119.tar
##rz
exit(go back to windows)
```
Step3 - download to windows from linux
```
scp user@host:/home/*user_name*/logs/logs.1119.tar C:\Users\*user_name*\logs
(input password)
Done
```







