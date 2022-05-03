VoltPop Jitsi Implementation
=========

Jitsi is an open source video conferencing solution that can be hosted in a docker instance.

Requirements
------------

The value `jitsi` *must* appear in client.roles

This role requires the following values:
* jitsi.url
* jitsi.ipaddr
* jitsi.version

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
    - name: Include jitsi
      include_role:
        name: jitsi
      vars:
        customer: "{{ client }}"
```
Invocation:

`ansible-playbook /path/to/playbook -e varsfile="$ANSIBLE_HOME/vars/varsfile.yml" -K --ask-vault-pass`
