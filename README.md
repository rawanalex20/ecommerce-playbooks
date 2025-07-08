# Description
Ecommerce playbooks is a slightly enhanced version of playbooks used in kodekloud Advanced Ansible Course labs to deploy kodekloud sample ecommerce application. The application consists of a webserver and a database server on two seperate hosts. The playbook uses roles that perform the deployment for each of the servers beside a playbook that clears the whole deployment.
# Dependencies
Versions used:
- ansible-core 2.14.17
- Python 3.9.19
- pip 25.1.1
- vault 1.20.0

Distro: Rocky 9.8
# Setup
To setup the environment download the repo on the controller node and adjust the hosts configurations in the inventory file and playbook directives to match your local hosts setup.
# Credentials
As a simulation to managing real world projects credentials hashicop vault lookup plugin is used. This provides a secured and dynamic way of retreiving the secrets. To setup a vault server follow steps in [hashicorp-vault-server-setup](https://github.com/rawanalex20/hashicorp-vault-server-setup) repository. 

Before running the playbook, install hvac module and hashi_vault collection and login in vault
```
pip3 install hvac
ansible-galaxy collection install community.hashi_vault
vault login -method=userpass username=admin
```

To use them as plaintext or encrypted by ansible vault simply replace the values in group_vars.
