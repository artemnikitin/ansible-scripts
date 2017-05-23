# ansible-scripts
Ansible scripts for automating manual tasks

### Setup
Add env variables:
```shell
export ANSIBLE_HOSTS=/path/to/hosts
export ANSIBLE_ROLES_PATH=/path/to/roles
export ANSIBLE_VAULT_PASSWORD_FILE=/path/to/vault_password

# Disable verification by .known-hosts file
export ANSIBLE_HOST_KEY_CHECKING=False
```

### Run
Run with command like:    
`ansible-playbook -s playbook_name.yml -u root`
