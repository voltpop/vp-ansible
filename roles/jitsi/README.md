Jitsi Set up
=========

Jitsi is an open source video conferencing solution that can be hosted in a docker instance.

Requirements
------------

This role requires the following values:
* jitsi_url
* jitsi_ipaddr
* jitsi_version

and is designed to run on a dockerhost.

Role Variables
--------------

All role variables are imported from a passed in vars file. see Requirements.


Dependencies
------------

This playbook depends on the continued maintenance of https://github.com/jitsi/docker-jitsi-meet. 

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

APLv2

