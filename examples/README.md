# Ansible Usage


## Use `ansible-galaxy install` before running `ansible-playbook` command
```
$ ansible-galaxy install -r requirements.yml -p ./roles -vvv
```


# Deploy with ansible-playbook

## Executing a playbook command like the following:
```
$ ansible-playbook -i inventory_hosts --extra-vars "version=1.2.3 other_variable=foo" playbook.yml -vvv
```
