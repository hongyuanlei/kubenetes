# Setup Kubernetes Cluster with Vagrant
link: https://blog.devops.dev/how-to-setup-kubernetes-cluster-with-vagrant-e2c808795840

## Install virtual machine
```shell
$ brew install --cask vagrant virtualbox
```


## Config the shared folder path
Update the infrastructure/settings.yaml
```shell
shared_folders:
  - host_path: /Users/ylhong/workspace/vagrant/kubernetes/app
    vm_path: /home/vagrant/workspace/app
```
## Start vagrant

```shell
$ cd infrastructure/
$ vagrant up
```

## SSH master node

```shell
$ vagrant ssh master
```

## Show k8s nodes
```shell
$ kubectl get nodes -o wide

NAME            STATUS   ROLES           AGE   VERSION   INTERNAL-IP   EXTERNAL-IP   OS-IMAGE             KERNEL-VERSION      CONTAINER-RUNTIME
master-node     Ready    control-plane   15d   v1.26.1   10.0.0.10     <none>        Ubuntu 22.04.2 LTS   5.15.0-67-generic   cri-o://1.26.4
worker-node01   Ready    worker          15d   v1.26.1   10.0.0.11     <none>        Ubuntu 22.04.2 LTS   5.15.0-67-generic   cri-o://1.26.4
worker-node02   Ready    worker          15d   v1.26.1   10.0.0.12     <none>        Ubuntu 22.04.2 LTS   5.15.0-67-generic   cri-o://1.26.4
```

