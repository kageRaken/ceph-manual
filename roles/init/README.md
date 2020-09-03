Node initialization
===================

A brief description of the role goes here.

Connects to the basic templated node  which will boot as a member of the vanilla group and completes some actions.

- Configures provided ip.
- Configures provided hostname

Role Variables
--------------

Cli variables that are not provided when running the role will cause it to fail.

- init_cli_ip_hostid: provide the host part of the ip to be configured. 
  (ex: for a 192.168.100.123/24 ip , the cli_ip_hostid should be "123".)
- init_cli_hostname: provide the hostname of the initialized node.

Example Playbook
----------------

```
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
```

License
-------

BSD

