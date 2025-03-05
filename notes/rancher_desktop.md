
# Linux VM for containers/pods

To get access to the VM, use:

    rdctl shell

That will give you a _ash_ shell into the VM. You can use _sudo_ after to get admin rights.

Rancher Desktop use [lima](https://lima-vm.io) to manage the virtual machine that runs Alpine Linux as the host for Docker/moby or containerd.

On macOS, the lima instance (including the disk) in located at:

    /Users/<your_user>/Library/Application\ Support/rancher-desktop/lima/0

When using [reverse-sshfs](https://lima-vm.io/docs/config/mount/) to manage the volumes, it will mount a couple of volumes by default from the computer than runs Rancher Desktop. 

On macOS, when the VM engine is VZ or QEMU, the following mounts will be avaible:

    :/Users/<your_user>     926.4G    362.8G    563.6G  39% /Users/<your_user>
    :/tmp/rancher-desktop   926.4G    362.8G    563.6G  39% /tmp/rancher-desktop
    :/Volumes               926.4G    362.8G    563.6G  39% /Volumes
    :/var/folders           926.4G    362.8G    563.6G  39% /var/folders
    :/private/tmp           926.4G    362.8G    563.6G  39% /private/tmp
    :/private/var/folders   926.4G    362.8G    563.6G  39% /private/var/folders

The following mount will be added only if you use VZ as the VM engine:

    vz-rosetta              926.4G    362.8G    563.6G  39% /mnt/lima-rosetta

To decide if you need to use VZ or QEMU, check the [decision diagram](https://lima-vm.io/docs/config/vmtype/) in Lima's documentation.

If you wish to have persistent directories for the containers that will run on the Linux VM, make sure it's stored on your computer in one of the paths that are mounted (but it's a bit scary that /Volumes is mounted, since it allows access to your whole disk). If you store data for containers directly in the VM outside a path that is not mounted from your Mac, you will loose the data when the VM is recreated, like when Rancher Deskop is upgraded.

If you create directories for mounts defined in Helm charts, etc, those directories must be reachable with the user UID 10001, so make sure you change the owner of those directories to 10001, or set a ACL on it (DON'T do a _chmod 0777_ on those!).