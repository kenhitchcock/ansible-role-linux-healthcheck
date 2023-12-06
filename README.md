# Ansible Role: linux-healthcheck 

Installs and runs a series of checks to determine the general health of a Linux system.

## Requirements

This role currently is only supported (runs) on RHEL 8 & 9. The systems this is run against will require access to Red Hat repositories to install packages if you choose to do so. A variable file can be included in your playbook if you would like to override the defaults:

    - hosts: database
      var_file: 
        - /path/to/vars/file
      roles:
        - role: ansible-role-linux-healthcheck
          become: yes

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

Below is a list of all basic variables used throughout the role.

| Variable | Description | Required | Defaults |
|:--------:|:-----------:|:--------:|:--------:|
| **linux_healthcheck_skip_package_install** | This variable dictates if packages will be installed | Yes | false |
| **linux_healthcheck_oscap_profile** | This variable dictates if packages will be installed | Yes | false |
| **linux_healthcheck_skip_package_install** | This variable dictates if packages will be installed | Yes | false |
| **linux_healthcheck_skip_package_install** | This variable dictates if packages will be installed | Yes | false |

## Dependencies

None.

## Example Playbook

    - hosts: linuxserver
      become: yes
      vars_files:
        - vars/main.yml
      roles:
        - ansible-role-linux-healthcheck

*Inside `vars/main.yml`*:

    linux_healthcheck_skip_package_install: false
    linux_healthcheck_oscap_profile: xccdf_org.ssgproject.content_profile_cis
    linux_healthcheck_oscap_policy: ssg-rhel9-ds
    linux_healthcheck_oscap_reports: "/tmp/openscap_reports"


## License

MIT / BSD

## Author Information

This role was created in 2023 by [Ken Hitchcock](https://github.com/kenhitchcock).

