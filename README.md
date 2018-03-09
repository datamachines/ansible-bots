## Ansible construction example

- Requires Ansible 2.0 or newer
- Expects Ubuntu 14.04 + hosts

These playbooks deploy a very basic implementation of elastic search Server. 
To use them, first edit the "hosts" inventory file to contain the
hostnames of the machines on which you want elasticsearch deployed, and edit the 
group_vars/all/all.yml file to set any elastic search configuration parameters you need.

Then run the playbook, like this:

	ansible-playbook -i hosts -v site.yml

When the playbook run completes, you should be able to see the elastic search
Application Server running on the ports you chose, on the target machines.

