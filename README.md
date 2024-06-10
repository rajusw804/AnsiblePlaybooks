Ansible : Redhat  
		  Python

Configuration Management tools : chef,puppet,saltstack

Ansible : Opensource 
          Agent less
		  SSH Mechanism
		  Push Mechanism
		  Module support
		  
		  
	Ad-hoc
	Playbooks
	Roles
	tower
	Vault
	
Master :
	     	  ssh-keygen
       
		  /root/ssh/id_rsa.pub
		  
		  sudo amazon-linux-extras install epel
		  yum install ansible pip -y
		  ssh root@agentPublicIP
		  
		  ansible --version
		  
		  
	Agent:
 	      ssh-keygen
	
	      copy  master /root/ssh/id_rsa.pub to agent's /root/ssh/authrozied_keys
		  
vi /etc/ansible/ansible.cfg  -> Main configuration File

inventory      = /etc/ansible/hosts
sudo_user      = root

remove # before above 2 lines


vi /etc/ansible/hosts  -> inventory File
[agents]
13.234.119.49 ansible_user=root


Ad-hoc:
ansible agents -m ping
ansible agents -m yum -a "name=git state=present"
ansible agents -m copy -a "src=/opt/abc.txt dest=/opt/abc.txt"
ansible agents -m yum -a "name=httpd state=absent"
ansible agents -m service -a "name=httpd state=started"
ansible agents -m service -a "name=httpd state=stopped"
