# Kubeadm-Ansible

Ansible playbooks for deploying a Kubernetes cluster using kubeadm for 3 master nodes.

## Repository Contents

- **common.yaml**: This file includes all tasks that apply universally to all nodes within the cluster. This may include security updates, installation of basic utilities, and any other common configurations needed across the cluster.

- **masters.yaml**: This is install and configure the master nodes. Tasks in this playbook include the installation of Kubernetes master components.

- **workers.yaml**: Responsible for setting up the worker nodes. This playbook includes tasks for installing Kubernetes worker components like kubelet, and for joining these nodes to the Kubernetes cluster.

- **network.yaml**: Handles the network configuration for the Kubernetes cluster, which could involve setting up network plugins like Calico or Weave, and ensuring proper network policies and overlay networks are in place.

- **hosts.ini**: An inventory file for Ansible, which lists all the nodes in the cluster along with their roles and connection details.

## License

This project is licensed under the terms of the [LICENSE](LICENSE) file located in the repository.

## Usage

To use these playbooks, ensure you have Ansible installed and configured on your management machine. Update the `hosts.ini` file to reflect your environment's configuration. Run the playbooks using the following commands:

```bash
ansible-playbook -i hosts.ini common.yaml
ansible-playbook -i hosts.ini masters.yaml
ansible-playbook -i hosts.ini workers.yaml
ansible-playbook -i hosts.ini network.yaml
```

## Contributing

Contributions to this project are welcome! Please fork the repository and submit pull requests with any enhancements, bug fixes, or improvements.
