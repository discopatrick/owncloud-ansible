# OwnCloud Ansible project

## TODO

* ansible-pull vault decryption issue - dump db with mysql cli without the need for giving a password - perhaps with a passwordless user? Or 
* Install python >= 2.7.9 to fix SSL certificate errors when downloading apt repo keys. Remove current 'validate_certs: no' setting
* install and enable ClamAV antivirus?
* research best practice for storing credentials on the server
* general server hardening

## Useful things to remember

* When using a box via the terminall manually, to open a shell as a specific user, you can do: `sudo -u www-data -s`
* Here's an example of running ansible-playbook directly: `ansible-playbook --private-key=../.vagrant/machines/default/virtualbox/private_key -u vagrant backup.yml`
	* don't forget to disable host checking if it will help during dev (in ansible.cfg)
	* also specify the inventory file in ansible.cfg
* Command to run the permissions script as a one-off task: ansible phansible-web -m script -a ./files/owncloud_permissions.sh -u vagrant --private-key=../.vagrant/machines/default/virtualbox/private_key --become
* ownCloud has issues importing db dumps from other environments, so use separate S3 buckets for each of dev, staging, and production.
