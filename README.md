# Ansible Role: Package

#### Version: 1.1.1

[![pipeline status](https://gitlab.com/sparknsh/ansible-role-package/badges/master/pipeline.svg)](https://gitlab.com/sparknsh/ansible-role-package/commits/master)
[![Ansible Role](https://img.shields.io/ansible/role/29019.svg)](https://galaxy.ansible.com/sparknsh/package)
[![Ansible Role](https://img.shields.io/ansible/role/d/29019.svg)](https://galaxy.ansible.com/sparknsh/package)

Development of this project is managed in a private repository then pushed out to [GitLab](https://gitlab.com/sparknsh/ansible-role-package) and [GitHub](https://github.com/sparknsh/ansible-role-package) when we have a new version for you. If you have any issues please contact [sparknsh](https://www.sparknsh.com/contact?type=issue&name=ansible-role-package)

## Role Variables

    package_list: []

##### APT package manager variables

    package_apt_repo_https: False
    package_apt_repo_source: True
    package_apt_repo_backports: True
    package_apt_repo_experimental: True
    package_apt_repo_contrib_nonfree: True
    package_apt_repo_custom:
      - name: ""
        repo_url: "" # Do not include "https://" or "http://"
        repo_src: False
        key: ""
        filename: "" # Do not include ".list" in the filename
        state: present

##### YUM package manager variables

    package_yum_epel: True
    package_yum_repo_custom:
      - name: ""
        baseurl: ""
        gpgcakey: ""
        gpgcheck: ""
        enable: ""
        filename: "" # If not set name is used. By setting this you can add multiple repos into one file.
        state: present


#### Example

    package_list:
      - tree
      - nload
      - name: net-tools
        yum: False
      - name: htop
        state: absent
      - name: iotop
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
