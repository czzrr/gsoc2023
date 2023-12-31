# Google Summer of Code 2023

## Project background

[virtiofs](https://virtio-fs.gitlab.io/) is a shared file system specialized for virtual machines (VMs).
[virtiofsd](https://gitlab.com/virtio-fs/virtiofsd) is the daemon (background proces) for virtiofs that handles VM requests to the file system.
To protect its users, virtiofsd provides several sandboxing mechanisms to restrict its own access rights.
The options are to sandbox by using either Linux namespaces or chroot.


## Project description
The main goal of the project was to create [a sandboxing tool for virtiofsd](https://wiki.qemu.org/Google_Summer_of_Code_2023#A_sandboxing_tool_for_virtiofsd) instead of having sandboxing code in virtiofsd itself.
The motivation for this is increased flexibility when integrating virtiofsd into other tools such as virtual machine monitors and containers.

## Contributions

### Development of an external sandboxing tool for virtiofsd ([link to PR](https://gitlab.com/virtio-fs/virtiofsd/-/merge_requests/182))
**Status:** draft PR

The majority of the project duration was spent on creating a tool that can do the sandboxing for virtiofsd.
Through the usage of Linux namespaces, the external tool creates an isolated environment just for virtiofsd to execute in, increasing the overall security of the application.

### Adding support to virtiofsd for sandboxing via Landlock, a Linux kernel security module ([link to PR](https://gitlab.com/virtio-fs/virtiofsd/-/merge_requests/179))
**Status:** partially approved PR

The goal of this additional task was to add Landlock as a sandboxing option to virtiofsd.
Landlock is a Linux kernel feature that allows unprivileged processes to isolate themselves.
This was accomplished by creating safe wrappers for the Landlock system calls and using them when the user wishes sandboxing to be done through Landlock.
    
## Experiments
###  My notes and experiments for learning about sandboxing techniques and technologies ([link to repository](https://gitlab.com/czzrr/sandboxing))
This repository contains my own notes and experiments for technologies such as chroot, pivot_root, namespaces, capabilities and Landlock.
This gave me the required knowledge for a successful experience while working on my contributions to virtiofsd.

## Next steps
- Finish the merge request for the external sandboxing tool.
- Currently the external sandboxing tool uses namespaces for sandboxing. Additionally, add support for sandboxing via Landlock like virtiofsd has.