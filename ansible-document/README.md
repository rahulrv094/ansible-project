
### Chapter 1: Introduction to Ansible & Use Cases

---

## What is Ansible?

Ansible is an open-source IT automation engine that automates configuration management, application deployment, cloud provisioning, and many other IT tasks.

---

## Why Ansible is Used in DevOps?

| 🟢 Easy Reasons                      | 📘 Official Strengths                  |
| ------------------------------------ | -------------------------------------- |
| No software needed on target servers | Agentless – uses SSH for communication |
| Very easy to learn – YAML syntax     | Human-readable automation language     |
| Works on cloud, VMs, containers      | Platform-independent                   |
| Safe to run repeatedly               | Idempotent automation                  |
| Scales easily                        | Supports large infrastructure          |

---

## How Ansible Works (Architecture)

Ansible follows a simple architecture consisting of the following components:

- **Control Node**: The machine where Ansible is installed (usually your laptop or CI server).
- **Managed Nodes**: The servers you want to configure (no agent needed, just SSH access).
- **Inventory**: A file listing target machines (static or dynamic).
- **Modules**: Reusable units that perform actions (e.g., install packages, restart services).
- **Playbook**: A YAML file that defines what to do.

### Example of a Playbook

```yaml
- hosts: webservers
  tasks:
    - name: Install Nginx
      apt:
        name: nginx
        state: present
````

---

### Visual Diagram (Simple)

```
           +---------------------+
           |     Control Node    |
           |   (Ansible CLI)     |
           +----------+----------+
                      |
            SSH Connection (Agentless)
                      |
        +-------------+-------------+
        |             |             |
   +----+----+   +----+----+   +----+----+
   | Host 1  |   | Host 2  |   | Host 3  |
   +---------+   +---------+   +---------+

     (Managed Nodes - target servers)
```

---

## Summary

* You run Ansible on the **Control Node**.
* It connects to multiple **Managed Nodes** over **SSH**.
* Tasks in **Playbooks** use **Modules** to perform actions on those nodes.
* No software installation is needed on the **Managed Nodes**.

---

## Real-World Use Cases for DevOps

| Use Case            | Example                                    |
| ------------------- | ------------------------------------------ |
| Install software    | Install Docker on 100 servers              |
| Configure servers   | Set up Nginx or firewall rules             |
| Deploy applications | Push new app version to staging or prod    |
| Automate updates    | Run OS updates every week                  |
| Set up Kubernetes   | Install kubeadm/kubectl automatically      |
| CI/CD               | Run Ansible from Jenkins or GitHub Actions |

