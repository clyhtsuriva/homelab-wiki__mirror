# Talos OS Installation on Proxmox

## Talos Factory Image Configuration
Generated using [Talos Image Factory](https://factory.talos.dev/?arch=amd64&cmdline-set=true&extensions=-&extensions=siderolabs%2Fintel-ucode&extensions=siderolabs%2Fqemu-guest-agent&platform=nocloud&target=cloud&version=1.9.4) with the following options:

- **Architecture:** `amd64`
- **Platform:** `nocloud`
- **Target:** `cloud`
- **Version:** `1.9.4`
- **Kernel Command Line Set:** None
- **Extensions:**
  - ✅ `siderolabs/qemu-guest-agent` (for Proxmox VM management)
  - ✅ `siderolabs/intel-ucode` (for Intel CPU microcode updates)

For more details, visit [Talos OS Documentation](https://www.talos.dev/).

## Schematic Ready
Shematic ID : `e3fab82b561b5e559cdf1c0b1e5950c0e52700b9208a2cfaa5b18454796f3a7e`
```
customization:
    systemExtensions:
        officialExtensions:
            - siderolabs/intel-ucode
            - siderolabs/qemu-guest-agent
```

## First Boot

Here are the options for the initial boot of Talos Linux on Nocloud:

#### Disk Image

`https://factory.talos.dev/image/e3fab82b561b5e559cdf1c0b1e5950c0e52700b9208a2cfaa5b18454796f3a7e/v1.9.4/nocloud-amd64.raw.xz`

#### ISO

`https://factory.talos.dev/image/e3fab82b561b5e559cdf1c0b1e5950c0e52700b9208a2cfaa5b18454796f3a7e/v1.9.4/nocloud-amd64.iso`

#### PXE boot (iPXE script)

`https://pxe.factory.talos.dev/pxe/e3fab82b561b5e559cdf1c0b1e5950c0e52700b9208a2cfaa5b18454796f3a7e/v1.9.4/nocloud-amd64`
