#### Design a Kubernetes cluster.

#### Install Kubernetes masters and nodes, including the use of TLS bootstrapping.

#### Configure secure cluster communications.

#### Configure a Highly-Available Kubernetes cluster.

#### Know where to get the Kubernetes release binaries.

A Kubernetes binary release includes all the Kubernetes binaries as well as the supported release of etcd.

- kubelet
- kube-proxy
- kube-apiserver
- kube-controller-manager
- kube-scheduler


Method 1

```
$ wget https://github.com/kubernetes/kubernetes/releases/download/v1.9.0/kubernetes.tar.gz

$ tar xvzf kubernetes-manifests.tar.gz

$ cd kubernetes

$ KUBERNETES_SKIP_CONFIRM=skip KUBERNETES_SERVER_ARCH=amd64 KUBE_VERSION=v1.9.0  bash   cluster/get-kube-binaries.s

$ cd server

$ tar xvzf kubernetes-server-linux-amd64.tar.gz

$ tree kubernetes
kubernetes
├── addons
├── kubernetes-src.tar.gz
├── LICENSES
└── server
    └── bin
        ├── apiextensions-apiserver
        ├── cloud-controller-manager
        ├── cloud-controller-manager.docker_tag
        ├── cloud-controller-manager.tar
        ├── hyperkube
        ├── kubeadm
        ├── kube-aggregator
        ├── kube-aggregator.docker_tag
        ├── kube-aggregator.tar
        ├── kube-apiserver
        ├── kube-apiserver.docker_tag
        ├── kube-apiserver.tar
        ├── kube-controller-manager
        ├── kube-controller-manager.docker_tag
        ├── kube-controller-manager.tar
        ├── kubectl
        ├── kubelet
        ├── kube-proxy
        ├── kube-proxy.docker_tag
        ├── kube-proxy.tar
        ├── kube-scheduler
        ├── kube-scheduler.docker_tag
        ├── kube-scheduler.tar
        └── mounter

3 directories, 26 files
```

Method 2
```
$ export KUBE_VERSION=v1.9.0

$ echo 'for binary in kube-apiserver  kube-controller-manager kube-scheduler kubectl kubelet ; do
    wget https://storage.googleapis.com/kubernetes-release/release/$KUBE_VERSION/bin/linux/amd64/$binary
done' | bash -x
```

#### Provision underlying infrastructure to deploy a Kubernetes cluster.

#### Choose a network solution.

#### Choose your Kubernetes infrastructure configuration.

#### Run end-to-end tests on your cluster.

#### Analyse end-to-end tests results.

#### Run Node end-to-end tests.
