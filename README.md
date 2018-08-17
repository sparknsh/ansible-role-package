# Ansible Role: Package

#### Version: 1.0.0

[![pipeline status](https://gitlab.com/sparknsh/ansible-role-package/badges/master/pipeline.svg)](https://gitlab.com/sparknsh/ansible-role-package/commits/master)
[![Ansible Role](https://img.shields.io/ansible/role/29016.svg)](https://galaxy.ansible.com/sparknsh/package)
[![Ansible Role](https://img.shields.io/ansible/role/d/29016.svg)](https://galaxy.ansible.com/sparknsh/package)

Development of this project is managed in a private repository then pushed out to [GitLab](https://gitlab.com/sparknsh/ansible-role-package) and [GitHub](https://github.com/sparknsh/ansible-role-package) when we have a new version for you. If you have any issues please contact [sparknsh](https://www.sparknsh.com/contact?type=issue&name=ansible-role-package)

## Role Variables

    package_list: []
    package_list_host: []
    package_list_group: []
    package_state: "present"
    package_update_cache: True
    package_cache_valid_time: 3600


#### Example

    package_list:
      - name: nginx
      - name: htop
        state: absent
      - name: apache
        apt: False


## Example Playbook

    - hosts: all
      vars_files:
        - vars/main.yml
      roles:
         - { role: sparknsh.package }

## License

MIT

## Author Information

This role was created in 2018 by [sparknsh](https://www.sparknsh.com) at [Rebel Media, Inc.](https://www.rebelmedia.io/)
