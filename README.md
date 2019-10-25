Role Name
=========

The role is intended to be used to install minishift as it is reported in official OKD docs for LINUX:

[Setting Up the Virtualization Environment](https://docs.okd.io/latest/minishift/getting-started/setting-up-virtualization-environment.html) 
<br>
[Installing Minishift](https://docs.okd.io/latest/minishift/getting-started/installing.html)

Requirements
------------

No particular requirements needed

Role Variables
--------------

**docker_machine_driver_url**
URL for docker machine driver url, needs to fit the required version and architecture. Can be retrieved [here](https://github.com/dhiltgen/docker-machine-kvm/releases)

**minishift_url**
URL for minishift release, needs to fit the required version and architecture. Can be retrieved [here](https://github.com/minishift/minishift/releases)

**os_user**
The user you want to install minishift for. Defaults to {{ ansible_user_id }}.

**install_dir**
The directory where you want minishift installed into. Defaults to /home/{{ os_user }}/minishift

Dependencies
------------

This role has no dependencies

Example Playbook
----------------

To install minishift for user minishift.

    - hosts: servers
      roles:
         - role: install_minishift
           os_user: minishift
           install_dir: /path/to/install
           docker_machine_driver_url: https://url/to/correct/release
           minishift_url: https://url/to/correct/release


