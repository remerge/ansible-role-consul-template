# Ansible Role for Consul Template

Install consul-template repository and packages with Ansible.

## [Example Playbook](#example-playbook)

```yaml
---
- name: Setup Consul-template
  hosts: all
  become: yes
  gather_facts: yes
  roles:
    - role: remerge.consul-template
```

## [Role Variables](#role-variables)

The default values for the variables are set in
[`defaults/main.yml`](defaults/main.yml):

```yaml
---
# location of consul-template configuration file
consul_template_config_dir: /etc/consul-template
consul_template_consul_address: "localhost:8500"
```
