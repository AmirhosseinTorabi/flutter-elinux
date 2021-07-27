# Flutter for Embedded Linux (eLinux)
This software is a **non-official** extension to the [Flutter SDK](https://github.com/flutter/flutter) to build Flutter apps for Embedded Linux devices.

**It is still been developed! So, currently, there is a lot of unsupported functions yet.**

## Quick start
### How to insall flutter-elinux
```Shell
$ git clone https://github.com/sony/flutter-elinux.git
$ sudo mv flutter-elinux /opt/
$ export PATH=$PATH:/opt/flutter-elinux/bin
```

### Install other tools
```Shell
$ sudo apt install curl clang cmake pkg-config
# If you want to use Weston as a Wayland compositor:
$ sudo apt install weston
```

### How to run flutter sample app in Weston
You need to install a Wayland compositor such as Weston and launch it before launching your Flutter apps.

```Shell
$ flutter-elinux devices
3 connected devices:

eLinux (desktop) • elinux-wayland • flutter-tester • Ubuntu 20.04.2 LTS 5.8.0-63-generic
eLinux (desktop) • elinux-x11     • flutter-tester • Ubuntu 20.04.2 LTS 5.8.0-63-generic
```

```Shell
$ flutter-elinux create sample
$ cd sample
$ weston &
$ flutter-elinux run -d elinux-wayland
```

If you want to run your flutter app in X11, use `elinux-x11` instead of `elinux-wayland`:
```Shell
$ flutter-elinux run -d elinux-x11
```

### How to run flutter sample app in X11
```Shell

```

## Documentation
See https://github.com/sony/flutter-elinux/wiki

## Contributing
See [CONTRIBUTING.md](CONTRIBUTING.md).

## Companion repos
| Repo | Purpose |
| ------------- | ------------- |
| [flutter-elinux](https://github.com/sony/flutter-elinux) | Flutter tools for eLinux |
| [flutter-elinux-plugins](https://github.com/sony/flutter-elinux-plugins) | Flutter plugins for eLinux |
| [flutter-embedded-linux](https://github.com/sony/flutter-embedded-linux) | eLinux embedding for Flutter |
| [meta-flutter](https://github.com/sony/meta-flutter) | Yocto recipes of eLinux embedding for Flutter |

## Base software
This software was created based on the [flutter-tizen](https://github.com/flutter-tizen/flutter-tizen) (branched from [this version](https://github.com/flutter-tizen/flutter-tizen/commit/ed128233c0bce33c77dd0df69afa59f0888d2d00)). Special thanks to the flutter-tizen team.
