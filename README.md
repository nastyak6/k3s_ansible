# K3s Ansible Automation

This repository contains an Ansible playbook to automate the installation and configuration of a K3s (Lightweight Kubernetes) cluster. The setup supports both master and worker nodes, making it ideal for local development, testing, and air-gapped environments.

## Features

- Install K3s master and worker nodes.
- Support for offline (air-gapped) installation.
- Customizable configurations using Ansible.
- No external downloads during the installation (all binaries are included).
- Handles master-worker node setup.

## Prerequisites

Ensure the following prerequisites are met before running the playbook:

- **Operating System**: Ubuntu (preferred) or any compatible Linux distribution.
- **Ansible**: Installed on the control machine.
- **Python**: Installed on the control machine.
- **K3s binaries**: Downloaded and included in the repository (for air-gapped environments).
- **Root access**: On the target machines.

### Install Ansible

To install Ansible on Ubuntu:

```bash
sudo apt update
sudo apt install -y ansible
```

## Clone the Repository

Clone this repository to your local machine:

```bash
git clone https://github.com/nastyak6/k3s_ansible.git
cd k3s_ansible
```

## Update LocalHost IP
in playbook.yml -> change the k3s_master_ip to the desired IP address.

### 3. Run the Playbook

Run the Ansible playbook script to install K3s on your nodes:

```bash
./run_playbook.sh
```

This will:
1. Move binaries to the correct location in your setup.
2. Install K3s on the master node.
3. Join the worker nodes to the K3s cluster.

### 4. Verify the Installation

After the playbook runs, verify that the cluster is up and running:

```bash
kubectl get nodes
```


##### GAPS
Tried installing on localhost both the Master and Agent, no success. 
Keep getting unauthorized issue:

```bash
curl -k -H "Authorization: Bearer $TOKEN" https://10.0.2.15:6443
{
  "kind": "Status",
  "apiVersion": "v1",
  "metadata": {},
  "status": "Failure",
  "message": "Unauthorized",
  "reason": "Unauthorized",
  "code": 401
}
```
Hence project installs the Master node but no agents ATM.
