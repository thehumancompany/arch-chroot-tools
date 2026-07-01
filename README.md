[comment]: <> (SPDX-License-Identifier: AGPL-3.0)

[comment]: <> (-------------------------------------------------------------)
[comment]: <> (Copyright © 2024, 2025, 2026  Pellegrino Prevete)
[comment]: <> (All rights reserved)
[comment]: <> (-------------------------------------------------------------)

[comment]: <> (This program is free software: you can redistribute)
[comment]: <> (it and/or modify it under the terms of the GNU Affero)
[comment]: <> (General Public License as published by the Free)
[comment]: <> (Software Foundation, either version 3 of the License.)

[comment]: <> (This program is distributed in the hope that it will be useful,)
[comment]: <> (but WITHOUT ANY WARRANTY; without even the implied warranty of)
[comment]: <> (MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the)
[comment]: <> (GNU Affero General Public License for more details.)

[comment]: <> (You should have received a copy of the GNU Affero General Public)
[comment]: <> (License along with this program.)
[comment]: <> (If not, see <https://www.gnu.org/licenses/>.)

# Arch Ch(ange) Root Tools

Some scripts for running stuff from an Arch Linux
ephemeral live cd using classic chroots or more
modern systemd machinery.

It's really just a bunch of temporary scripts I've written
to speed up running a graphical environment from the `releng`
archiso profile system (the Arch Linux install drive)
I'vebeen temporarly using (lol 3 years) before I will have
restarted Life and
[DogeOS](
  https://github.com/themartiancompany/dogeos)
public build system and of which the only ones I really use
are `zram-setup` and `chroot-shell`, which starts a `systemd-nspawn`
container able to run a graphical environment.

The reason one needs these updated tools as one can't really rely
on classic `chroot` is these days `dbus` is set up by default
to interact with `systemd` so if you don't run your system into a cgroup
container you're gonna get into issues with many os functions.

If you read the code you may read I've tried adding support for
passing the sound card to the container as well but I haven't really
still tried to have it working.

If you do that please contribute back the change.

# How to use

After you've mounted your os somewhere (i.e. `/mnt`),
just run

```bash
chroot-shell \
  "/mnt"
```

You may want to be a

## Installation

The tools in this source repo
can be installed from source using GNU Make.

```bash
make \
  install
```

The collection has officially published on the
the uncensorable
[Ur](
  https://github.com/themartiancompany/ur)
user repository and application store as
`arch-chroot-tools`.
The source code is published on the
[Ethereum Virtual Machine File System](
  https://github.com/themartiancompany/evmfs)
so it can't possibly be taken down.

To install it from there just type

```bash
ur \
  arch-chroot-tools
```

A censorable HTTP Github mirror of the recipe published there,
containing a full list of the software dependencies needed to run the
tools is hosted on
[arch-chroot-tools-ur](
  https://github.com/themartiancompany/arch-chroot-tools-ur).

Be aware the mirror could go offline any time as Github and more
in general all HTTP resources are inherently unstable and censorable.

## License

This program is released by Pellegrino Prevete under the terms
of the GNU Affero General Public License version 3.
