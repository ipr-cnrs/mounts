# Mounts

1. [Overview](#overview)
2. [Role Variables](#role-variables)
3. [Example Playbook](#example-playbook)
4. [Configuration](#configuration)
5. [Development](#development)
5. [License](#license)
6. [Author Information](#author-information)

## Overview

Manage to mount local and remote devices.

## Role Variables

* **mounts_list** : Directory that must contains all informations about devices to mount.
* **mounts_list.name** : The path to the mountpoint.
* **mounts_list.src** : Path to the local or remove device.
* **mounts_list.fstype** : Device filesystem type.
* **mounts_list.opts** : Mount options [default : `defaults,noatime`].
* **mounts_list.state** : If the device should be 'mounted', 'present',… [default : `present`].

## Example Playbook

* Use defaults vars :

``` yml
- hosts: serverXYZ
  roles:
    - role: ipr-cnrs.mounts
      mounts_list:
        - name: /mnt/storage
          src: 'nfs-share.domain.org:/mnt/share'
          fstype: nfs4
          opts: 'defaults,x-systemd.automount,x-systemd.device-timeout=2,x-systemd.idle-timeout=1min,noatime,noauto'
          state: mounted
```

## Configuration

This role will :
* Create the mountpoint directory.
* Add an entry in `/etc/fstab`.
* Ensure to mount the device if specified.
* Restart systemd's filesystem.target to ensure automount device works.

## Development

This source code comes from our [Gogs instance][mounts source] and the [Github repo][mounts github] exist just to be able to send the role to Ansible Galaxy…

But feel free to send issue/PR here :)

Thanks to this [hook][gogs to github hook], Github automatically got updates from our [Gogs instance][mounts source] :)

## License

[WTFPL][wtfpl website]

## Author Information

Jérémy Gardais
* Source : [on IPR's Gogs][mounts source]
* [IPR][ipr website] (Institut de Physique de Rennes)

[vars directory]: ./vars
[gogs to github hook]: https://stackoverflow.com/a/21998477
[mounts source]: https://git.ipr.univ-rennes1.fr/cellinfo/ansible.mounts
[mounts github]: https://github.com/ipr-cnrs/mounts
[wtfpl website]: http://www.wtfpl.net/about/
[ipr website]: https://ipr.univ-rennes1.fr/
