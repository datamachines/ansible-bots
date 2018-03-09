## Ansible construction example

- Requires Ansible 2.0 or newer
- Expects Ubuntu 14.04 + hosts

These playbooks deploy a very basic implementation of server roles.


### Elastic Search Server. 
To use them, first edit the "hosts" inventory file to contain the
hostnames of the machines on which you want elasticsearch deployed under section [elasticsearch-servers], and edit the 
group_vars/all/vars.yml file to set any elastic search configuration parameters you need.

Then run the playbook, like this:

	ansible-playbook -i hosts -v es.yml

When the playbook run completes, you should be able to see the elastic search
Application Server running on the ports you chose, on the target machines.

### NFS server
To use them, first edit the "hosts" inventory file to contain the
hostnames of the machines on which you want NFS server deployed in section [nfs-servers], and edit the 
group_vars/nfs-servers/var.yml file to set any nfs server configuration parameters you need.

Then run the playbook, like this:

	ansible-playbook -i hosts -v nfs.yml

To mount the nfs partition as client. 
mount -t nfs $nfs-server:/$nfs_export_filesystem $local_mount_point


### all roles
To use them, first edit the "hosts" inventory file to contain the
hostnames of the machines on each role, and edit the
group_vars/$role/var.yml file to set all variables.

Then run the playbook, like this:

        ansible-playbook -i hosts -v site.yml

