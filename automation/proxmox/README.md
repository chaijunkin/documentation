qm create 2004 --memory 2048 --net0 virtio,bridge=vmbr0 --scsihw virtio-scsi-pci
CHANGE NAME OF THE VM, boot order, os type, qemu agent, add cloudinit drive
qm importdisk 2004 Rocky-9-GenericCloud.latest.x86_64.qcow2 vm-store --format qcow2
qm template 2004


qm set 2004 --scsi0 vm-store:0,format=qcow2,import-from=Rocky-9-GenericCloud.latest.x86_64.qcow2
