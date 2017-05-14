Role Name
=========

This role is used to install a working rundeck, along with dependencies and the ec2 and ansible plugins.

Requirements
------------

a linux debian machine using apt

Role Variables
--------------

default vars are set in defaults/main.yml, you will need to change those to match whatever your ldap settings are, and whatever domain your rundeck will be on.


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: rundeck
      roles:
         - rundeck_setup

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
