Node initialization
===================

A brief description of the role goes here.

Connects to the basic templated node  which will boot as a member of the vanilla group and completes some actions.

- Configures provided ip.
- Configures provided hostname

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Cli variables that are not provided when running the role will cause it to fail.

- init_cli_ip_hostid: provide the host part of the ip to be configured. 
  (ex: for a 192.168.100.123/24 ip , the cli_ip_hostid should be "123".)
- init_cli_hostname: provide the hostname of the initialized node.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

---
- hosts: vanilla
  become: yes
  vars_prompt: 
    - name: init_cli_hostname
      prompt: "What is the node's hostname?"
      private: no

    - name: init_cli_ip_hostid
      prompt: "What will the host part of the node's ip be? (192.168.152.XXX)"
      private: no

  roles: 
    - init
  tags: init

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
