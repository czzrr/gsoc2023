# Google Summer of Code 2023

## Project description
The main goal of the project was to create [a sandboxing tool for virtiofsd](https://wiki.qemu.org/Google_Summer_of_Code_2023#A_sandboxing_tool_for_virtiofsd) that would increase flexibility when integrating virtiofsd into other tools.

## Contributions
- [Development of an external sandboxing tool for virtiofsd.](https://gitlab.com/virtio-fs/virtiofsd/-/merge_requests/182)
- [Adding support to virtiofsd for sandboxing via Landlock, a Linux kernel security module.](https://gitlab.com/virtio-fs/virtiofsd/-/merge_requests/179)

## Experiments
- [My notes and experiments for learning about sandboxing techniques and technologies.](https://gitlab.com/czzrr/sandboxing)
This gave me the required knowledge for a successful experience while working on my contributions to virtiofsd.

## Next steps
- Finish the merge request for the external sandboxing tool.
- Currently the external sandboxing tool uses namespaces for sandboxing. Additionally, add support for sandboxing via Landlock like virtiofsd has.