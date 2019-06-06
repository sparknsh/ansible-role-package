# Ansible Role: Package

#### Version: 1.1.3

[![](https://img.shields.io/badge/role-sparknsh.package-blue.svg)](https://galaxy.ansible.com/sparknsh/package)

Development of this project is managed in a private repository then pushed out to [GitLab](https://gitlab.com/sparknsh/ansible-role-package) and [GitHub](https://github.com/sparknsh/ansible-role-package) when we have a new version for you. If you have any issues please contact [sparknsh](https://www.sparknsh.com/contact?type=issue&name=ansible-role-package)

## Role Variables

```yaml
package_list_install:
  apt: []
  yum: []
  dnf: []

package_list_remove:
  apt: []
  yum: []
  dnf: []
```

##### APT package manager variables

```yaml
package_apt_repo_https: false
package_apt_repo_source: true
package_apt_repo_backports: true
package_apt_repo_experimental: true
package_apt_repo_contrib_nonfree: true
package_apt_repo_custom:
  - name: ""
    repo_url: "" # Do not include "https://" or "http://"
    repo_src: False
    key: ""
    filename: "" # Do not include ".list" in the filename
    state: present
```

##### YUM package manager variables

```yaml
package_yum_epel: true
package_yum_repo_custom:
  - name: ""
    baseurl: ""
    gpgcakey: ""
    gpgcheck: ""
    enable: ""
    filename: "" # If not set name is used. By setting this you can add multiple repos into one file.
    state: present
```

#### Example

```yaml
package_list_install:
  apt:
    - sudo
    - htop
  yum:
    - htop
  dnf:
    - htop

package_list_remove:
  apt:
    - net-tools
  yum:
    - tree
  dnf:
    - iotop
```

## Example Playbook

```yaml
- hosts: all
  vars_files:
    - vars/main.yml
  roles:
     - { role: sparknsh.package }
```

## License

MIT

## Author Information

This role was created in 2018 by [sparknsh](https://www.sparknsh.com) at [Rebel Media, Inc.](https://www.rebelmedia.io/)
