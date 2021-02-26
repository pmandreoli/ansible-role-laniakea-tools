ansible-role-laniakea-tools
=========

Role for the installation of flavor's tools and workflows on laniakea galaxy instances.

Requirements
------------

python3 pip3 libselinux-python3

Role Variables
--------------

``galaxy_flavors_recipes_url:``github repository containing flavor recipes default: ``https://github.com/pmandreoli/Galaxy-flavors-recipes.git``

``galaxy_flavors_recipes_tag:`` repository branch name (default ``test``)

``galaxy_admin_api_key:`` galaxy istance admin api_key (default:``"{{ GALAXY_ADMIN_API_KEY }}"``)

``galaxy_tools_base_dir:`` directory used to store galaxy flavors recipes (default: ``/data``)

``galaxy_flavors_recipes_dir:``  directory to clone the repo in (default: '{{ galaxy_tools_base_dir }}/Galaxy-flavors-recipes')

``laniakea_galaxy_flavor:`` galaxy-testing galaxy flavor to install (default: ``galaxy-testing``)

``galaxy_run_sh_dir:``  galaxy dir that contain run.sh script (default: ``/home/galaxy/galaxy/server``)

``galaxy_virtual_env:`` path to galaxy virtualenv (default: ``/home/galaxy/galaxy/venv``)

``galaxy_config_file:``  path to galaxy config file (default:``/home/galaxy/galaxy/config/galaxy.yml``)

``role_debug:`` bool debug variable (default: ``false``)


Dependencies
------------

role ansible-role-laniakea-galaxy


Example Playbook
----------------

```

--- 
- hosts: galaxyservers
  become: true
  vars:
    laniakea_galaxy_flavor: "galaxy-testing"
    galaxy_admin_api_key: "admin_key"
    role_debug: true
  roles:
    - ansible-role-laniakea-tools
```

License
-------

MIT

Author Information
------------------
Pietro Mandreoli
email: pietro.mandreoli@unimi.it
