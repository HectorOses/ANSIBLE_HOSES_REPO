Role Name
=========

This role allows installation and configuration of basic CentOS 7 appliations. 

The target is to run it just after installing a new CentOS server and to be run in the localhost (update if to run in other server)

Requirements
------------

### Clone the repository

```
cd ~
git clone https://wwwin-github.cisco.com/hoses/ANSIBLE_HOSES_REPO.git
cd ANSIBLE_HOSES_REPO
```

### Install Ansible

```
sudo yum install -y ansible
```

NOTE: if you get "Another app is currently holding the yum lock..."  
  1. Ctrl+C install  
  2. `ps -ef | grep yum` to find who is locking it, most probably automatic updates  
  3. Most probably this is the Software Update application waiting to update software.  
    3.1 you can kill the PID `sudo kill <PID>` as the ansible-playbook will update all , but BETTER:  
    3.2 Applications > System Tools > Software Update > Button:Install  

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

NOTE: Task "Disable SELinux at next reboot" will require reboot

The following is an example of an ansible-playbook using this role
```yml
---
- name: Installation of basic CentOS 7 utilities for hoses
  hosts: localhost
  roles:
    - role: centos_install
```

### Run Ansible Playbook

```
ansible-playbook centos_install_wRoles.yml --extra-vars 'ansible_become_pass=admin'
```

License
-------

BSD

Author Information
------------------

Hector Oses: oseszgz@gmail.com

PENDING TO ADD CENTOSBASE
-----------------------------
- New terminal shortcut
	https://stackoverflow.com/questions/26771044/how-do-i-make-a-keyboard-shortcut-for-terminal-in-centos-7

- Installs

	<...>

- code plugins, complete list as required
	```
	code --list-extensions
	code --install-extension ms-vscode.cpptools
	code --uninstall-extension ms-vscode.csharp
	```
- fix pip upgrade, looks like it's not working properly