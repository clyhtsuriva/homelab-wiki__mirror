# Set Up Homelab

## Create the VMs with OpenTofu

```sh
pushd opentofu/
./init-validate-plan.sh
tofu apply "plan.out"
popd
```

## Configure them with Ansible

```sh
export ANSIBLE_CONFIG="$HOME/workbench/homelab-iac/ansible/ansible.cfg"
ansible-playbook ~/workbench/homelab-iac/ansible/playbooks/bootstrap.yml
```


## Destroy

```sh
pushd opentofu/
tofu destroy
popd
```
