# CMPE272_AssignmentOne_Ansible
Prerequisites:
  1. Ansible should be installed on primary/deployer VM.
  2. SSH trust should be enabled between primary/deployer VM and client VM on which webserver is supposed to be installed.
  3. Copy deploy_apache_webserver.yml, updeploy_apache_server.yml and index.html to /etc/ansible directory on primary/deployer VM.

Webserver deployment:
  1. Update /etc/ansible/hosts file to add a new group {{groupName}} with associated client host IP addresses.
     For example:
     [{{groupName}}]
     client_host_ip_address ansible_ssh_user={{username}}
     
  2. Verify that ansible inventory is updated to reflect newly added server group using command "ansible-inventory --list -y".
  3. Make sure that all the host in ‘[apache]’ group are pingable using command "ansible {{groupName}}" -m ping".
  4. Deploy webserver using command "ansible-playbook deploy_apache_webserver.yml".
  5. Un-deploy webserver using command "ansible-playbook undeploy_apache_webserver.yml".
