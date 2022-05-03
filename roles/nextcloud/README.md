VoltPop NextCloud and Office Implementation
=========

NextCloud and Collabora are both open source cloud friendly implementations of common productivity tools, including:
* Shared calendars
* File synchronization
* File sharing and multi-tenant editing
* Secure online file storage and upload

Requirements
------------

The value `nextcloud` *must* appear in client.roles

This role requires the following values:
* nextcloud.url
* nextcloud.ipaddr
* nextcloud.version

and is designed to run on a dockerhost.

Role Variables
--------------

See requirements

Dependencies
------------

This role depends on the continued maintenance of the docker images listed in files/docker-compose.yml

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
