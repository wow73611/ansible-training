# Ansible installation

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
