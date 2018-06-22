# Ansible Installation

## Requirements

- Linux Ubuntu 14.04, 16.04 or CentOS 7.x
- virtualenv >= 1.11.0
- ansible >= 2.1
- pip == 7.1.2

## Install dependencies

- Ubuntu
```
$ sudo apt-get update
$ sudo apt-get install -y git build-essential libssl-dev libffi-dev sshpass
$ sudo apt-get install -y python-dev python-pip python-virtualenv
```

- CentOS
```
$ yum install -y git gcc gcc-c++ kernel-devel make openssl-devel libffi-devel sshpass
$ yum install -y python-devel python-pip python-virtualenv
```

## Upgrade pip
```
$ sudo pip install --upgrade pip==7.1.2
$ hash -r # Ubuntu14.04 only
```

## Install Ansible in virtualenv and active virtualenv
```
$ cd ~/your_project/
$ virtualenv venv
$ source venv/bin/activate
$ pip install ansible==2.1
```


# Ansible Usage

## Use `ansible-galaxy install` before running `ansible-playbook` command
```
$ ansible-galaxy install -r requirements.yml -p ./roles -vvv
```


## Run ansible playbook
The `ansible-playbook` command options:
```
  -e EXTRA_VARS, --extra-vars=EXTRA_VARS
                        set additional variables as key=value or YAML/JSON
  -i INVENTORY, --inventory-file=INVENTORY
                        specify inventory host path
                        (default=/etc/ansible/hosts) or comma separated host
                        list.
  -t TAGS, --tags=TAGS  only run plays and tasks tagged with these values
  -v, --verbose         verbose mode (-vvv for more, -vvvv to enable
                        connection debugging)
  --list-hosts          outputs a list of matching hosts; does not execute
                        anything else
  --list-tags           list all available tags
  --list-tasks          list all tasks that would be executed
```

Running a playbook with `ansible-playbook` command like the following:
```
$ ansible-playbook -i inventory_hosts -e "version=1.2.3 other_variable=foo" -e @vars.yml playbook.yml -vvv
```

## Specified tags

- Display all tags:
  $ ansible-playbook -i inventory_hosts playbook.yml --list-tags

- Specify the tag:
  $ ansible-playbook -i inventory_hosts playbook.yml --tags "ntp"

- Skip the tag:
  $ ansible-playbook -i inventory_hosts playbook.yml --skip-tags "keepalived,haproxy"


# Reference & Appendices

- [Installation Guide](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)
- [User Guide](https://docs.ansible.com/ansible/latest/user_guide/index.html)
- [Best Practices](https://docs.ansible.com/ansible/latest/user_guide/playbooks_best_practices.html)
- [Module Index](https://docs.ansible.com/ansible/latest/modules/modules_by_category.html)
