## Ansible Kubespray

I successfully tested this in my homelab, where it performed flawlessly. However, for production use, its deployment, upgrade process, and feature set are not as desirable as those offered by RKE2.

## RKE2

I found RKE2 to be the easiest to deploy and upgrade. It works without any preliminary setup. It is made by Rancher, a well-known company that provides support for and makes Kubernetes engines.

## Others

Honorable mentions: Kubesphere, Kubekey, K3s, RKE. I have explored storage solutions like Portworx and OpenEBS but found them unnecessary for my personal projects, as I decided against deploying databases in Kubernetes. Additionally, I evaluated cluster backup solutions including Velero, Stash K8, and Kasten K10.

# RKE2 Kubernetes Cluster Management

## Remove all RKE2 nodes

To remove all nodes from the RKE2 cluster, use the following command:

```bash
sudo ansible-playbook ansible/playbooks/rke2/uninstall-rke2.yml
```

## Install RKE2 nodes

To install nodes in the RKE2 cluster, execute:

```bash
sudo ansible-playbook ansible/playbooks/rke2/install-rke2-cluster.yml
```

## Install a single RKE2 node

To install a single node (e.g., `node2` as the master, ensure it's in the `kube_control_plane` group):

```bash
sudo ansible-playbook ansible/playbooks/rke2/install-rke2-cluster.yml --limit node2
```

## Remove a single RKE2 node

To remove a specific node (e.g., `node2`) from the cluster, use:

```bash
sudo ansible-playbook ansible/playbooks/rke2/uninstall-rke2.yml --limit node2
```
