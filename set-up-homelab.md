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
export ANSIBLE_CONFIG="./ansible/ansible.cfg"
ansible-playbook ./ansible/playbooks/bootstrap.yml
```


## Destroy

```sh
pushd opentofu/
tofu destroy
popd
```
