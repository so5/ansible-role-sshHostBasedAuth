ssh hostbased auth
=========

allow ssh hostbased authentication from specified hosts on both root and non-root user.
also set ssh client to use host based auth.

Requirements
------------

none.

Role Variables
--------------
```
ssh_hostbased_auth_allowed_hosts: []       #ip address or hostname of host which will be allowd to access to target machine.
ssh_hostbased_auth_only: False             #if true, preferred access will be restricted to hostbased authentication
ssh_hostbased_auth_server: True            #set up server setting
ssh_hostbased_auth_client: True            #set up client setting (/etc/ssh/ssh_config)
ssh_hostbased_auth_keyscan_retry: 6        #num retries for ssh-keyscan
ssh_hostbased_auth_keyscan_retry_delay: 10 #delay time between each keyscan
```

Dependencies
------------

dnspython package is required.

Example Playbook
----------------
```
- hosts: all
  roles:
    - { role: so5.ssh_hostbased_auth, ssh_hostbased_auth_allowed_hosts: ["192.168.0.2", "192.168.0.4"] }
```

License
-------

MIT

Author Information
------------------

This role is created by Naoyuki Sogo.