# Ansible Role: Dynu Updater

## Description

Ansible role to deploy **Dynu Updater** Docker containers, keeping your Dynu DNS records updated with your current public IP address.

The Docker image used by this role can be found here:
[https://hub.docker.com/r/longkeyy/dynu-updater](https://hub.docker.com/r/longkeyy/dynu-updater)

## Requirements

* Docker (must be installed on the target hosts)

## Installation

```bash
ansible-galaxy install cornelcristea.dynu_updater
```

## Variables

The role uses the following variables:

| Nme | Default | Description |
| -------------  | ------ | ---------- |
| `dynu_username` | *(empty)* | Your Dynu username |
| `dynu_password` | *(empty)* | Your Dynu IP Update Password (**not** your account password) |
| `dynu_hosts` | *(empty)*   | List of hostnames that will be updated by the role |
| `dynu_docker_image` | `longkeyy/dynu-updater:1.1` | Docker image for the container |
| `dynu_base_dir` | `/opt/dynu` | Directory where the `docker-compose.yml` file will be stored |

## Playbook Example

```yaml
- hosts: servers
  roles:
    - role: cornelcristea.dynu_updater
  vars:
    dynu_hosts:
      - myapp.freeddns.org
      - myblog.freeddns.org
```

## How to Contribute

We welcome contributions! Here’s how you can help improve this role:

1. **Fork the repository**    
  Click the `Fork` button at the top of the repository.

2. **Clone your fork locally**

```bash
git clone https://github.com/cornelcristea/ansible-role-dynu-updater.git
cd ansible-role-dynu-updater
```

3. **Create a new branch**

```bash
git checkout -b my-feature-branch
```
  * Make your changes following Ansible best practices.
  * Add or update tests if applicable.
  * Update the README for any new variables or features.
  * Test your changes:
```bash
ansible-playbook test.yml -i inventory
```

4. **Commit and push your changes**

```bash
git add .
git commit -m "Add feature XYZ"
git push origin my-feature-branch
```

5. **Open a Pull Request (PR)**   
Submit a PR from your branch. Include a clear description of your changes and why they’re needed.

### We appreciate your contributions!
