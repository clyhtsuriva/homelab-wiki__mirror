# Helper scripts for Proxmox

## [Proxmox Clean Orphaned LVM](https://community-scripts.github.io/ProxmoxVE/scripts?id=clean-orphaned-lvm)

> This script helps Proxmox users identify and remove orphaned LVM volumes that are no longer associated with any VM or LXC container. It scans all LVM volumes, detects unused ones, and provides an interactive prompt to delete them safely. System-critical volumes like root, swap, and data are excluded to prevent accidental deletion.

[Source Code](https://raw.githubusercontent.com/community-scripts/ProxmoxVE/main/misc/clean-orphaned-lvm.sh)

As a privileged user :
```sh
bash -c "$(wget -qLO - https://github.com/community-scripts/ProxmoxVE/raw/main/misc/clean-orphaned-lvm.sh)"
```

## [Proxmox VE Post Install](https://community-scripts.github.io/ProxmoxVE/scripts?id=post-pve-install)

> This script provides options for managing Proxmox VE repositories, including disabling the Enterprise Repo, adding or correcting PVE sources, enabling the No-Subscription Repo, adding the test Repo, disabling the subscription nag, updating Proxmox VE, and rebooting the system.

[Source Code](https://raw.githubusercontent.com/community-scripts/ProxmoxVE/main/misc/post-pve-install.sh)

As a privileged user :
```sh
bash -c "$(wget -qLO - https://github.com/community-scripts/ProxmoxVE/raw/main/misc/post-pve-install.sh)"
```
