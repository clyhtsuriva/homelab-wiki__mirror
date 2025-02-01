# UFW rules management using Ansible

Since ufw is part of the community.general collection, ensure it's installed on the Ansible control machine:

```sh
ansible-galaxy collection install community.general
```

It is by default installed and enabled with ALLOW rules for SSH, HTTP and HTTPS on all images generated for this homelab.

The tasks are defined in `ansible/roles/common/tasks/ufw.yml`.

It is called by `ansible/playbooks/common.yml`.
