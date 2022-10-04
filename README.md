# Ansible-create-delete-and-assign-linux-user-to-group
Automate user administration with ansible playbooks

**Content:**<br>
createuser.yml<br>
deluser.yml<br>
copyssh.yml<br>

### In this repository are three ansible playbooks to mange user administration with linux (tested with ubuntu):<br>

**createuser.yml:** <br>creates a new user (name is defined in row 6, password is define in row 7) and assign the user to one or more groups (define in row 19)<br><br>
**deluser.yml** <br>deletes a user (defined in row 6) with the option to - try to - remove the users home directory (defined in row 13)<br><br>
**copyssh.yml** <br>adds a public ssh key in text form (defined in row 17) to the ".ssh/authorized_keys" file of a user defined in row 9 of a remote linux server (tested with ubuntu)<br><br>

### Install ansible on administration server (ubuntu)
sudo apt-get install -y ansible

### Define hosts in ansible hosts file
sudo vi /etc/ansible/hosts

#### Hosts should be defined in the following format<br>
[hostgroup1]<br>
IP1<br>
IP2<br>
...<br><br>
[hostgroup2}<br>
IP3<br>
IP4<br>
...<br><br>


| Ansible playbook commands | Description |
| ------ | ------ |
| ansible-playbook ***playbookname***.yml | Run playbook |
| ansible-playbook ***playbookname***.yml --list-hosts | List all hosts affected by playbook |
| ansible-playbook ***playbookname***.yml --limit ***hostgroup1*** | Run Playbook only for specific hostgroup hostgroup1 |
