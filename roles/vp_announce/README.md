VoltPop Announcer Server
=========

VoltPop Announcer (vp-announce) is a Python3 Flask based front-end for Redis. This service uses a docker instance of redis to handle the Pub/Sub backend.

Requirements
------------

The value `vp-announce` *must* appear in client.roles

This role requires the following values:
* vp_announce.stuff

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
    - name: Include vp-announce
      include_role:
        name: vp-announce
      vars:
        customer: "{{ client }}"
```
Invocation:

`ansible-playbook /path/to/playbook -e varsfile="$ANSIBLE_HOME/vars/varsfile.yml" -K --ask-vault-pass`
