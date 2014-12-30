Oracle Instant Client Deployment Role
=====================================

The [dareko.oracle_client](https://galaxy.ansibleworks.com/list#/roles/469) role deploys
the Oracle Instant Client and cx_Oracle python package on a target host.  
It requires the Oracle Instant Client installation files downloaded from the Oracle site.

Requirements
------------

This role requires Ansible 1.4 or higher and Instant Client installation files.
Platform requirements are listed in the Supported Platforms section of the role details.

Instant Client installation files can be downloaded from [Oracle site](http://www.oracle.com/technetwork/database/features/instant-client/index-097480.html).

The following files have to be downloaded and copied to the `files` directory:

- instantclient-basiclite-linux.*.zip
- instantclient-sdk-linux.*.zip
- instantclient-sqlplus-linux.*.zip

**NOTE:** The cx_Oracle python package is compatible with Oracle 11g client only. Do not install Oracle 12c client if you want to use cx_Oracle.

Role Variables
--------------

The variables that can be passed to this role with default values are as follows.

    # installation base directory
    oracle_client_base: /opt/oracle
    
    # location of the instant client zip files on the local machine
    oracle_client_local_oracle_zip_files_dir: /tmp/ansible/files

Dependencies
------------

None

Example Playbook
----------------

1. Add a group to the `hosts` inventory file

        [oracle_client]
        host.domain

2. Add role to the `site.yml` file

        - hosts: oracle_client
          sudo: true
          roles:
          - { role: dareko.oracle_client, oracle_client_base: /usr/local }

3. Run the `site.yml` playbook

        ansible-playbook -i hosts site.yml

License
-------

BSD

Author Information
------------------

[Darek Owczarek](https://galaxy.ansibleworks.com/list#/users/1102)
