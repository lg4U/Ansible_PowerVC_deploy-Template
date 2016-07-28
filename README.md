# Ansible_PowerVC_deploy-Template
Role Name
=========
Deploy-Template_PowerVC provide an Ansible role to deploy a VM with a PowerVC Template (AIX or Linux image).

Requirements
------------
This Role use the PowerVC API to provide AIX or Linux on Power VM. So you must have set a PowerVC System before using it, and Templates available. 

Role Variables
--------------

This Role includes any variables that are in vars/main.yml:
- __IP_PVC__		     :	 PowerVC server IP or Hostname 
- __URL_PVC__		     :	 Url to contact PowerVC server
- __URL_CLERK__		   :	 Url to contact Cloud Manager PowerVC
- __PVC_USER__		   :	 PowerVC User login
- __PVC_PWD__	  	   :	 PowerVC User password
- __PAUSE_IN_SEC__	 :	 Pause before Poll Status (secondes)
- __nb_retry__		   :	 Retries Number to poll Status 
- __nb_delay__		   :	 Delay between Polling (secondes)
- __nb_timeout__	   :	 Timeout waiting Active VM (secondes)
- __SSH_PUBLIC_KEY__ :   absolute_path for public ssh keyfile

Example Playbook
----------------

How to use this role. You must have a PowerVC Template available. For instance, I have a template based on an AIX image AIX 7.1 TL3 SP5. Its name is MOD_AIX7100-03_05.
You have to specify the VM_NAME to deploy and the PROJECT_NAME to use this role.

By default, PowerVC use 'ibm-default' project. On my PowerVC, I created a project named 'devops-project':

```
# ansible-playbook DeployVM_PowerVC.yml -e TEMPLATE_NAME=MOD_AIX7100-03_05 -e PROJECT_NAME=devops-project -e VM_NAME=vm_test
```


Author Information
------------------

Author: Girardin Ludovic
