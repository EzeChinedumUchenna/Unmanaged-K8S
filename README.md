# Automating the deployment of a Managed Kubernetes on a VM using Ansible

First thing to do is to connect from your control host to the remote device(s) using SSH-based communication. Ansible uses SSH to connect to remote hosts and execute commands.Therefore generate SSH keys on the control host using the command below and go to ```~/.ssh ``` directory and copying the public key ```id_rsa.pub``` to the authorized_keys file on the remote devices. 
```
ssh-keygen
```

Inventory: Ensure that you have an inventory file (hosts) that lists the IP addresses or hostnames of the remote devices you want to manage with Ansible. This file typically resides in /etc/ansible/hosts or in a custom location specified by the -i flag.

 the configuration file ansible.cfg allows you to set various options and defaults for your Ansible setup. 
* host_key_checking = False: This option disables host key checking. When set to False, Ansible won't prompt you to confirm the authenticity of a host's SSH key when connecting. This is useful for automation tasks where you don't want the playbook execution to pause for manual 
*inventory = inventory: This option specifies the location of the inventory file
