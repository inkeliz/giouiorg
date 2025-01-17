---
title: Linux
---

## Dependencies

For Linux you need development packages for:

* Wayland
* x11, xkbcommon
* GLES, EGL
* libXcursor

Depending on your distribution, you may also need to install a Vulkan driver for best performance. Distributions like Arch do not do this automatically. You can check if you have working Vulkan support with the `vulkaninfo` command.

### Fedora 28+

On Fedora 28 and newer, install the dependencies with the command:

``` sh
dnf install gcc pkg-config wayland-devel libX11-devel libxkbcommon-x11-devel mesa-libGLES-devel mesa-libEGL-devel libXcursor-devel mesa-vulkan-devel
```

### Ubuntu 18.04+

On Ubuntu 18.04 and newer, use:

``` sh
apt install gcc pkg-config libwayland-dev libx11-dev libx11-xcb-dev libxkbcommon-x11-dev libgles2-mesa-dev libegl1-mesa-dev libffi-dev libxcursor-dev libvulkan-dev
```

## Building

To test whether the installation works, run:

``` sh
go run gioui.org/example/hello@latest
```

You can build Gio programs without X11 support with the `nox11` build tag:

``` sh
go run --tags nox11 gioui.org/example/hello@latest
```

To build Gio programs without Wayland support use `nowayland` build tag:

``` sh
go run --tags nowayland gioui.org/example/hello@latest
```
