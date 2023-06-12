Ansible Role: Move Home Directory to New Partition
=========

An Ansible role to move the home directory to a new partition on CentOS 8.

Requirements
------------

- This role assumes you have a new disk attached to the system.

- This role cannot be executed while the /home folder.

Role Variables
--------------
The block device (disk) where to operate.

    parted_device: /dev/sdb

If specified and the partition does not exist, will set filesystem type to given partition.
    parted_fs_type: xfs

Dependencies
------------

[ansible-galaxy-requirements.yml](ansible-galaxy-requirements.yml)

You can install these collections using the following commands:

```shell
ansible-galaxy role install -r ansible-galaxy-requirements.yml
```

Example Playbook
----------------

    - hosts: all
      become: true
      vars:
        parted_device: /dev/sdb
        parted_fs_type: xfs
      roles:
        - ansible-role-migrate-home-dir

License
-------

MIT / BSD

Author Information
------------------

* Author: Jody WAN
* Linkedin: https://www.linkedin.com/in/jodywan/
* Website: https://www.jodywan.com
