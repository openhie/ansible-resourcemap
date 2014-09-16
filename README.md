ansible-resourcemap
=========

Role for installing and deploying [resourcemap](https://github.com/instedd/resourcemap).

Role Variables
--------------

    # Controls whether to deploy from local deb
    resourcemap_deploy: false
    # Location of the deb to deploy if above is set to true
    resourcemap_deb_loc:
    # fqdn of server, default to detect fqdn.
    resourcemap_fqdn: "{{ansible_fqdn}}"

Example Playbook
----------------

    - hosts: servers
      roles:
         - ansible-resourcemap

      resourcemap_deploy: true
      resourcemap_deb_loc: resourcemap_2.12.deb

License
-------

Apache v2

Author Information
------------------
Ryan Yates
