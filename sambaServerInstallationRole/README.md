sambaServerInstallationRole
===========================

Custom Ansible role for integration of Linux Samba Server with MS Domain Services.

Requirements
------------

Suppose that you already have a valid Ansible installation.
Suppose that your potential Samba server(s) has a possibility to install 
some required repos from Internet or from Repository server instances.

Important! This role is specialized for Oracle Linux, Red Hat, CentOS OSs! 

Role Variables
--------------

"ansible.cfg" > A configuration file for this role only
"hosts" > Hostname(s) or IP-address(es) of potential Samba server(s)

All variables are listed in vars/main.yml.

Here, down below, a list of special variables:

{{ dirPaths.sambaDirPath }} > Path to the Samba share (for example: /opt/samba/share)

{{ domainCreds.username }} > An MS AD username(login) with appropriate domain privileges to join computer with AD Domain

{{ domainCreds.domainname }} > AD FQDN itself

{{ domainCreds.password }} > A password for the privileged username

{{ smbConfVars.wgName }} > NetBIOS Domain name (for example for domain.local NetBIOS name will be DOMAIN)

{{ smbConfVars.dcHostName }} > FQDN of Domain Controller

{{ smbConfVars.domainName }} > AD FQDN itself

{{ smbConfVars.validUserLogin }} > A username who will work with Samba share(s). 
Also with this username one of tasks performs a test connection to Samba server to verify permissions.

Important! If you want to add a whole group to access Samba share please look inside templates/smb.conf.j2. There you
will discover it.

Dependencies
------------

There are no dependencies yet.

Example Playbook
----------------

There is no example playbook. 

License
-------

BSD-3-Clause

Author Information
------------------

Yuri P. Bodrov. bodrovyp@hotmail.com. 
