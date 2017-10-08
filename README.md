# Introduction
This repo contains a Proof of Concept for a Elasticsearch, Logstash and Kibana stack.

# Dependencies
* Virtualbox
* Vagrant
* A file called encrypted_variables.yml in this directory

## How to create the encrypted_variables.yml in this directory?
```
git clone git@github.com:masterdam79/elk-test.git
cd elk-test
ansible-vault create encrypted_variables.yml
```

# Deployment

## Vagrant
I use Vagrant in combination with Virtualbox so this Proof of Concept is reproducible on any platform meeting these dependencies.

### Start Virtualbox machines
Run ```vagrant up``` to turn on all the machines

### Snapshot Virtualbox machines
Run ```vagrant snapshot save init``` to save snapshots called 'init' for all machines.

### Restore snapshots
Run ```vagrant snapshot restore init``` to restore snapshots called 'init' for all machines.

## Ansible
Running the Ansible playbook is as simple as ```ansible-playbook -i hosts -b playbook.yml``` as the hosts file already contains a reference to the private keys generated by Vagrant.