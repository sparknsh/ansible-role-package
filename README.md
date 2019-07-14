# Ansible Role: Package

#### Version: 1.2.1

[![](https://img.shields.io/badge/role-sparknsh.package-blue.svg)](https://galaxy.ansible.com/sparknsh/package)

Development of this project is managed in a private repository then pushed out to [GitLab](https://gitlab.com/sparknsh/ansible-role-package) and [GitHub](https://github.com/sparknsh/ansible-role-package) when we have a new version for you. If you have any issues please contact [sparknsh](https://www.sparknsh.com/contact?type=issue&name=ansible-role-package)

## Role Variables

```yaml
package__https: false
package__update_cache: true
package__cache_valid_time: 3600

package__list: []

package__list_host: []

package__list_group: []

package__custom_repo:
  apt: []
  yum: []

package__apt_source: false
package__apt_backports: true
package__apt_experimental: true
package__apt_contrib_nonfree: true

package__yum_epel: true
```

#### Example

```yaml
package__custom_repo:
  apt:
    - name: HAProxy
      repo_url: "deb https://haproxy.debian.net stretch-backports-1.9 main"
      key_url: "https://haproxy.debian.net/bernat.debian.org.gpg"
      state: present
      filename: haproxy
  yum: []

package__list:
  - name: sudo
  - name: htop
    dnf_ignore: true
  - name: haproxy
    apt_default_release: stretch-backports
    yum_ignore: true
    dnf_ignore: true
  - name: tree
    state: absent
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

This role was created in 2019 by [sparknsh](https://www.sparknsh.com) at [Rebel Media, Inc.](https://www.rebelmedia.io/)
