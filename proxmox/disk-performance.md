# Disk performance

Taken from https://forum.proxmox.com/threads/virtio-scsi-vs-virtio-scsi-single.28426/

> VirtIO SCSI vs VirtIO SCSI Single boils down to a simple architectural choice that has real performance implications:
>
> Standard VirtIO SCSI uses one controller that handles up to 16 disks, while Single dedicates one controller per disk. This matters most when using IOThreads (iothread=1), because threads work at the controller level.
>
> When using IOThreads, Single shows significantly better performance (often 30-50% improvement) because each disk gets its own dedicated processing thread. Without IOThreads, the performance difference is minimal (typically less than 5%).
>
> So the choice is straightforward:
>
> >   Want maximum disk performance? Use Single + iothread=1
> >   Managing lots of disks with limited resources? Standard might be better to avoid thread overhead
> >   From the VM's perspective, they work exactly the same
>
> This explains why benchmarks consistently show better I/O performance with Single + iothread=1, while keeping the underlying architectural differences clear.

Which results in the following packer configuration :

```hcl
   ...
   # VM Hard Disk Settings
   scsi_controller = "virtio-scsi-single"

   disks {
     ...
     io_thread      = true
   }
   ...
```
