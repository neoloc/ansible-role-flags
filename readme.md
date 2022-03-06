flags Role
=========

This role will create flags for hacking CTF events. A flag is a text file with a unique string to verify a participant has infiltrated the system.

[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-neoloc.flags-blue.svg)](https://galaxy.ansible.com/neoloc/ansible-role-flags/)


Requirements
------------

N/A

Role Variables
--------------

Refer to the defaults/main.yml file

```yaml
# enable creation of flags
flags_create: false

# A secret code used to create the flag contents
flags_secret: !vault |
          $ANSIBLE_VAULT;1.1;AES256
          39323432353462396633326339343838383830313637356432373639306639346466303133353263
          6231363134643036363535623534313238646263626138660a613865373838333962633635653434
          62346431333866613061396162363631623931396235323935373837363765303862333632663035
          3065363433323130610a366132666336643936626466373436333136653662656230666165373061
          61373564323064323833396265316266643238303434646437353532316164646136

# only update flags when serial changes
flags_serial: 0

# flags to create
flags_files_all: []
flags_files_group: []
flags_files_host: []

# Example flags
#flags_files_all:
#  - name: flagname
#    path: /etc/some/path.txt
#    owner: admin
#    group: wheel
#    mode: '640'

```

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: all
      roles:
         - neoloc.flags

License
-------

See license.md

Author Information
------------------

[![Github](https://img.shields.io/badge/Github-neoloc-blue.svg)](https://github.com/neoloc)
