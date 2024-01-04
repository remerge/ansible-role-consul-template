# ansible-role-consul-template

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
      consul_template_templates_config:
    - source: "/path/in/server/template"
      destination: "/template/output/path/in/server"
      template_file: "/path/to/consul-template-file-in-ansible-project"
      perms: 0600
      command: "/bin/systemctl reload service"
      splay: "10s"
      user: "username"
      group: "groupname"
```

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/remerge/ansible-role-consul-template/blob/master/defaults/main.yml):

```yaml
---
consul_template_install_package: true
# should files in the same directory as the generated file be cleaned up?
consul_template_remove_unmanaged: false
# location of consul-template configuration file
consul_template_config_dir: /etc/consul-template
consul_address: "localhost:8500"
```
