![Download](https://xpra.org/icons/download.png)

Downloads are listed here for all the [supported platforms](./Platforms).\
For most use cases, you can install [any supported version](./Versions) on both client and server.

The source can be downloaded directly from https://github.com/Xpra-org/xpra, or using release snapshots:
* [github releases](https://github.com/Xpra-org/xpra/releases)
* [pypi releases](https://pypi.org/project/xpra/#history)
* [xpra.org](https://xpra.org/src/)

# ![Authentication](https://xpra.org/icons/authentication.png) Signatures
All the binary downloads are signed using the PGP key https://xpra.org/gpg.asc aka `F18AD6BB`, the key fingerprint is `C11C 0A4D F702 EDF6 C04F  458C 18AD B31C F18A D6BB`.
For rather [tedious reasons](https://github.com/Xpra-org/xpra/issues/3446), you may need to import two almost identical versions of this key to use the repositories on Debian systems.

***

# ![MS Windows](https://xpra.org/icons/win32.png) Microsoft Windows
The [microsoft windows download directory](https://xpra.org/dists/windows/) contains:

|Format|Purpose|Download Link|GPG Signature|
|------|-------|-------------|-------------|
|`EXE`|General purpose installer|[Xpra-x86_64_Setup.exe](https://xpra.org/dists/windows/Xpra-x86_64_Setup.exe)|[Xpra-x86_64_Setup.exe.gpg](https://xpra.org/dists/windows/Xpra-x86_64_Setup.exe.gpg)
|`MSI`|alternative installer for unattended installations|[Xpra-x86_64.msi](https://xpra.org/dists/windows/Xpra-x86_64.msi)|[Xpra-x86_64.msi.gpg](https://xpra.org/dists/windows/Xpra-x86_64.msi.gpg)|
|`ZIP`|local installation without administrative rights|[Xpra.zip](https://xpra.org/dists/windows/Xpra.zip)|[Xpra.zip.gpg](https://xpra.org/dists/windows/Xpra.zip.gpg)|

Other types of builds are also available there, ie: `Client` only builds without the server components - those use less disk space and.
Both 32-bit and 64-bit builds can be installed concurrently, but the file and URL associations will point to the installation performed last and these will be removed when either package is uninstalled.

The beta builds can be found here: https://xpra.org/beta/windows/

You can also install xpra using [MSYS2](http://www.msys2.org/) by running `pacman -S mingw-w64-x86_64-python3-xpra`. The only downside of using this method is the lack of file association, but you do get more control over which components and dependencies are and aren't installed.

***

# ![MacOS](https://xpra.org/icons/osx.png) MacOS
The [Mac OSX downloads](https://xpra.org/dists/MacOS/) directory contains:
|Format|Purpose|Download Link|GPG Signature|
|:-----|:------|------------:|------------:|
|x86_64 `DMG`|Disk Image|[Xpra.dmg](https://xpra.org/dists/MacOS/x86_64/Xpra.dmg)|[Xpra.dmg.gpg](https://xpra.org/dists/MacOS/x86_64/Xpra.dmg.gpg)
|x86_64 `PKG`|PKG Installer|[Xpra.pkg](https://xpra.org/dists/osx/x86_64/Xpra.pkg)|[Xpra.pkg.gpg](https://xpra.org/dists/MacOS/x86_64/Xpra.pkg.gpg)|

These MacOS packages are *not notarized*, please see [Can't you just right click?](https://lapcatsoftware.com/articles/unsigned.html) for installation.

If MacOS complains that the application is damaged, run: `sudo xattr -rd com.apple.quarantine /Applications/Xpra.app`

The beta MacOS builds can be found here: https://xpra.org/beta/MacOS

***

# ![Linux](https://xpra.org/icons/linux.png) Linux
The Linux stable repositories are all found here: https://xpra.org/dists/ \
The beta repositories are here: https://xpra.org/beta/  
Note: the beta repositories are supplemental ones so you must also enable the stable repository to be able to use them.


## ![RPM](https://xpra.org/icons/rpm.png) for RPM distributions:
* import the key used for signing the packages:\
```shell
rpm --import https://xpra.org/gpg.asc
```
* download the chosen repository file (stable or beta) into `/etc/yum.repos.d` as root, ie:\
Fedora: `wget -O /etc/yum.repos.d/xpra.repo https://xpra.org/repos/Fedora/xpra.repo` \
CentOS / RHEL: `wget -O /etc/yum.repos.d/xpra.repo https://xpra.org/repos/CentOS/xpra.repo`
* `dnf install xpra`

|Distribution|Stable Repository file|Beta Repository File|
|------------|---------------|--------------------|
|[Fedora](https://getfedora.org/)|https://xpra.org/repos/Fedora/xpra.repo|https://xpra.org/repos/Fedora/xpra-beta.repo|
|[CentOS](https://www.centos.org/)|https://xpra.org/repos/CentOS/xpra.repo|https://xpra.org/repos/CentOS/xpra-beta.repo|

The RPM repositories do not require any extra repositories to be added. \
Should you wish to do so, you can also [build your own packages](./Building-RPM).

## ![Debian](https://xpra.org/icons/debian.png) for Debian based distributions:
* ensure the SSL certificates are up to date:
`sudo apt install ca-certificates`
* import the key key used for signing the packages (newer Debian releases require a newer key):
```shell
sudo wget -O "/usr/share/keyrings/xpra-2022.gpg" https://xpra.org/xpra-2022.gpg
sudo wget -O "/usr/share/keyrings/xpra-2018.gpg" https://xpra.org/xpra-2018.gpg
```
For older distributions:
```shell
wget -q https://xpra.org/xpra-2022.gpg -O- | sudo apt-key add -
wget -q https://xpra.org/xpra-2018.gpg -O- | sudo apt-key add -
```
* download the appropriate repository file (see table below) into  `/etc/apt/sources.list.d` as root:\
`cd /etc/apt/sources.list.d;wget $REPOFILE`
* then run `apt update;apt install xpra`

|Distribution|Stable Repository file|Beta Repository File|
|:-----------|:--------------|:-------------------|
|[Debian Stretch](https://wiki.debian.org/DebianStretch)|https://xpra.org/repos/stretch/xpra.list|https://xpra.org/repos/stretch/xpra-beta.list|
|[Debian Buster](https://wiki.debian.org/DebianBuster)|https://xpra.org/repos/buster/xpra.list|https://xpra.org/repos/buster/xpra-beta.list|
|[Debian Bullseye](https://wiki.debian.org/DebianBullseye)|https://xpra.org/repos/bullseye/xpra.list|https://xpra.org/repos/bullseye/xpra-beta.list|
|[Debian Bookworm](https://www.debian.org/releases/bookworm/)|https://xpra.org/repos/bookworm/xpra.list|https://xpra.org/repos/bookworm/xpra-beta.list|
|[Ubuntu Bionic Beaver](https://wiki.ubuntu.com/BionicBeaver)|https://xpra.org/repos/bionic/xpra.list|https://xpra.org/repos/bionic/xpra-beta.list|
|[Ubuntu Focal Fossa](https://wiki.ubuntu.com/FocalFossa)|https://xpra.org/repos/focal/xpra.list|https://xpra.org/repos/focal/xpra-beta.list|
|[Ubuntu Impish Indri](https://launchpad.net/ubuntu/impish)|https://xpra.org/repos/impish/xpra.list|https://xpra.org/repos/impish/xpra-beta.list|
|[Ubuntu Jammy Jellyfish](https://releases.ubuntu.com/22.04/)|https://xpra.org/repos/jammy/xpra.list|https://xpra.org/repos/jammy/xpra-beta.list|


The DEB repositories may require the "universe" repository source to be activated to get all the features.


***

<details>
  <summary>Step by step example for installing the stable repository on Ubuntu Jammy Jellyfish</summary>

```
DISTRO=jammy
#install https support for apt (which may be installed already):
sudo apt-get update
sudo apt-get install apt-transport-https software-properties-common
sudo apt install ca-certificates
# add Xpra GPG key(s)
sudo wget -O "/usr/share/keyrings/xpra-2022.gpg" https://xpra.org/xpra-2022.gpg
# older distributions may also need:
# sudo wget -O "/usr/share/keyrings/xpra-2018.gpg" https://xpra.org/xpra-2018.gpg
# add Xpra repository
wget -O "/etc/apt/sources.list.d/xpra.list" https://xpra.org/repos/$DISTRO/xpra.list
# optional beta channel:
# wget -O "/etc/apt/sources.list.d/xpra-beta.list" https://xpra.org/repos/$DISTRO/xpra-beta.list
# install Xpra package
sudo apt-get update
sudo apt-get install xpra
```
For other distributions, simply change `DISTRO` to match your distribution name.
</details>