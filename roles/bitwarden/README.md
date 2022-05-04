VoltPop Bitwarden Implementation
=========

BitWarden is an open source password management solution that can be hosted in a docker instance.

Requirements
------------

The value `bitwarden` *must* appear in client.roles
An Installation ID and Installation key must be obtained from https://bitwarden.com/host/ 

This role requires the following values:
* bitwarden.version
* bitwarden.installation_id
* bitwarden.installation_key

and is designed to run on a dockerhost.

Role Variables
--------------

All role variables are imported from a passed in vars file. see Requirements.


Dependencies
------------

This playbook depends on the continued maintenance of https://github.com/jitsi/docker-jitsi-meet. 

Example Playbook
----------------
```
- hosts: localhost
  vars_files:
    - "{{ varsfile }}"
  tasks:
    - name: Include BitWarden
      include_role:
        name: bitwarden
      vars:
        customer: "{{ client }}"
```
Invocation:

`ansible-playbook /path/to/playbook -e varsfile="$ANSIBLE_HOME/vars/varsfile.yml" -K --ask-vault-pass`
