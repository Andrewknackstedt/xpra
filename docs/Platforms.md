Unless stated otherwise, all the operating systems listed here support all versions of xpra.\
The only architectures officially tested and supported are `i686` and `x86_64`, but xpra is also known to work on `ARM` and other CPU architectures.

Please make sure to test the latest [supported version](./Versions) before [reporting bugs](./Reporting-Bugs), you can [download it here](./Download).


# ![Linux](https://xpra.org/icons/linux.png) Linux

Distributions supported in the current [versions](./Versions):
|Distribution|Releases|
|------------|--------|
|Fedora| 36+|
|CentOS / RHEL|8.x and 9.x|
|Ubuntu|Bionic, Focal, Jammy, Kinetic|
|Debian|Buster, Bullseye, Bookworm, Sid|

## Architectures
The Linux repositories contain builds for `x86_64` and `arm64`.  
`x86` builds should work without any issues but builds are not provided in the repositories.

## Desktop Environments
The client should work with all window managers and desktop environments, though there may be some minor issues with the more exotic variants.  
Both X11 and Wayland environments are supported, but Wayland clients do not yet support quite as many features. (ie: no [Client OpenGL](https://github.com/Xpra-org/xpra/blob/master/docs/Usage/Client-OpenGL.md), more limited clipboard synchronization, etc)

***

# ![Windows](https://xpra.org/icons/win32.png) Microsoft Windows

Only Microsoft Windows versions 10 and 11 are actively supported.  
Windows 7 and Windows 8.x should also work.

***

# ![MacOS](https://xpra.org/icons/osx.png) MacOS
|Xpra Version|Mac OS Version|
|------------|--------------|
|v3.x|10.9 onwards|
|v4.x|10.12.x onwards|

The application is *not* notarized ([#2441](../../issues/2441) - [workaround](https://lapcatsoftware.com/articles/unsigned.html))

Binary builds are `x86_64` only, generating native `arm64` builds would require purchasing new hardware.

***

# ![BSD](https://xpra.org/icons/freebsd.png) BSD

All BSD variants should work, but are not regularly tested.

***

# Others

All other operating systems and architectures are not officially supported at present, but bug report and patches will be accepted.
