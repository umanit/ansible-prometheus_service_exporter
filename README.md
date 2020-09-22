# Ansible Role: service exporter

[![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg)](https://opensource.org/licenses/MIT)
[![GitHub tag](https://img.shields.io/github/v/tag/umanit/ansible-prometheus_service_exporter)](https://github.com/umanit/ansible-prometheus_service_exporter/tags)

## Description

Deploy prometheus [Tylux prometheus_service_exporter ](https://github.com/tylux/prometheus_service_exporter) using ansible.

Tylux service_exporter allow to monitor Linux services and is lightweigth than node_exporter


## Notes

Role forked and largely inspired by [Cloudalchemy Blackbox Exporter Ansible role](https://github.com/cloudalchemy/ansible-blackbox-exporter)

Role is supposed to work with Debian, Suse, RedHat, Fedora, (See [Ansible Galaxy meta](/meta/main.yml)), but it was only tested on Ubuntu Bionic (18.04).

## Requirements

- Ansible >= 2.7 (It might work on previous versions, but we cannot guarantee it)

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file.

Only two are defined: 
* service_exporter_version: version of service_exporter to install
* service_exporter_web_listen_address: IP and port to listen

The third is commented and must be defined : 
* service_exporter_service_list : list of service to monitor


## Example

### Playbook

Use it in a playbook as follows:
```yaml
- hosts: all
  vars:
    service_exporter_service_list:
      - apache2.service
  roles:
    - umanit.prometheus_service_exporter
```
## License

This project is licensed under MIT License. See [LICENSE](/LICENSE) for more details.
