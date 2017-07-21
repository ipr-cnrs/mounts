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

## Example Playbook

* Use defaults vars :

``` yml
- hosts: serverXYZ
  roles:
    - role: ipr-cnrs.mounts
```

## Configuration

This role will :
* Create the mountpoint directory.

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
