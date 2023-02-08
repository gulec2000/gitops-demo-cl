# gitops-demo-cl
GitOps Demo using Openshift Local, ArgoCD, HelmChart

## Instructions

### Install and Set up RedHat Openshift Local
Install RedHat Openshift Local(mac/windows/linux)
> It can be installed over **Redhat Openshift Local**

Setup RedHat Openshift Local on Terminal
```bash
 crc setup -b C:\Users\<your username>\.crc\cache\crc_hyperv_<version_number>_amd64.crcbundle
 crc start -b C:\Users\<your username>\.crc\cache\crc_hyperv_<version_number>_amd64.crcbundle -c 6 -d 32 -m 13222
 oc login -u kubeadmin -p <password>
 ```
> After setting up Openshift, just follow the instructions that appeared on terminal.

### Install Gitops Operator

> Open Openshift Console
> Go to Operator Hub
> Look for gitops Operator
> Install with default configurations

### Cluster-Admin Role to Argocd-application-Controller
```bash
oc login -u kubeadmin
oc adm policy add-cluster-role-to-user cluster-admin -z openshift-gitops-argocd-application-controller -n openshift-gitops
```
### Argocd

> Open Openshift Console
> Click on Square Button on top right besides alarm logo
> Open Cluster Argo CD. It opens in a new window
> go back to openshift console
> look for secret called openshift-gitops-cluster and copy the admin password
> go back to argocd
> login to argocd with username 'admin' and password
> there you are

### simple-app
we deploy an app over ocp. we use **oc apply** command
````bash
git clone https://github.com/gulec2000/gitops-demo-cl.git
cd gitops-demo-cl
oc apply -f simple-app/application.yaml
````




 
 

 
 
