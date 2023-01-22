### And why you should avoid them

Apart from the obvious danger of running versions without any security updates, there are other problems with downstream packages:
* often unusable builds, ie: [fedora : invalid mode 'start'](https://bugzilla.redhat.com/show_bug.cgi?id=1583319)
* invalid and unnecessary package dependencies (ie: `Fedora`)
* enabling untested options or dangerous codecs (all distros)
* missing features (ie: HTML5 with Debian packages)
* gratuitous patching, causing breakage [ie: Debian arm builds were unusable for years](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=921700)
etc

See also: [list of currently supported versions of xpra](./Versions).

You can download the official packages [here](https://github.com/Xpra-org/xpra/wiki/Download).

----

### Specific Distributions
A great explanation of the Debian / Ubuntu packaging mess can be found here: [​Matthew Garrett: There's more than one way to exploit the commons](https://mjg59.dreamwidth.org/41085.html) and also here: [Debian Distribution-Specific Issues](https://madaidans-insecurities.github.io/linux.html#debian).

The problems with the Ubuntu packages are so severe that they have [their own wiki page](./Distribution-Packages-Ubuntu)

Debian's hand waving about backports is rightfully ignored here.

----

# Proof

<details>
  <summary>3.0 release</summary>
 
This table was generated on the 2020-01-17 when 3.0.5 was the latest LTS version available.
| Distribution | Variant | Version Shipped | Known Issues |
| :----------- | :------ | :-------------- | :----------- |
|Fedora        |30 and 31| ​3.0.3           | OK: 3.0.5 in testing, their packaging unmercifully conflicts with the packages from xpra.org, also contains invalid and unnecessary dependencies|
|Ubuntu        |​Xenial aka 16.04| ​0.15.8   | over 4 years without any fixes, many known bugs and security vulnerabilities - do not use, very dangerous, missing components, etc|
|Ubuntu        |​Bionic aka 18.04| ​2.1.3    | 2.5 years without any fixes, numerous serious issues, dangerous|
|Ubuntu        |​Eoan aka 19.10|	​2.4.3	   |buggy, 14 months without any fixes|
|Debian        |​Buster   | ​2.4.3           |buggy, 14 months without any fixes|
|Debian        |​Stretch  | ​0.17.6          |3.5 years out of date, many known bugs and security vulnerabilities - do not use, very dangerous, missing components, etc|
|Gentoo        |​Stable   | ​2.2.2           |Dire: 2 years out of date!|
|Gentoo        |​Testing  | ​3.0.2           |Missing some important fixes, dubious patches applied
|​Arch          |n/a      | ​3.0.5           |Great: fully up to date|
</details>

<details>
  <summary>1.0 release</summary>

This table was generated on the 2017-03-18 when 1.0.4 was the latest LTS version available. (2.0 was released the day before)
| Distribution | Variant | Version Shipped | Known Issues |
| :----------- | :------ | :-------------- | :----------- |
|Fedora        |24 and 25| ​1.0             |missing critical updates|
|Ubuntu        |​Trusty aka 14.04| 0.12.3   |not a single fix applied in 3 years, dangerous|
|Ubuntu	       |Xenial aka 16.04| ​0.15.8   |16 months without any fixes, based on a dead branch|
|Debian        |​Jessie   |​0.14.10          |Awful: 2.5 years and 27 stable updates missing! Version no longer supported, includes known bugs, crashes and serious security vulnerabilities - dangerous!|
|Debian        |​Jessie-backports|0.17.6    |Backports an EOL version!?|
|Debian        |​Stretch  |0.17.6           |EOL version, known bugs and security vulnerabilities - do not use|
|Gentoo        |​Stable	​ |1.0.3	           |Not too bad: 1 minor update behind|
|Gentoo        |​Testing  |1.0.4            |Good: up to date!|
|​Arch          |n/a      |2.0              |Great: most up to date|
</details>

<details>
  <summary>0.14 release</summary>

This table was last updated 2015-12-28, when 0.15.10 was the latest version available. (0.14.33 for LTS branch).
| Distribution | Variant | Version Shipped | Known Issues |
| :----------- | :------ | :-------------- | :----------- |
|Fedora        |21 and 22| ​0.15.9          | Up to date (0.15.10 in "testing" queue)|
|Ubuntu        |​Precise aka 12.04|0.0.7.36 |Far too many to list - not a single bug fix applied in 4 years!|
|Ubuntu        |​Trusty aka 13.04|0.12.3    |Far too many to list - not a single bug fix applied in 2 years, avoid|
|Ubuntu        |​Vivid aka 15.04|0.14.10    |Awful: 23 stable updates missing! version no longer supported, known bugs including crashes and vulnerabilities - avoid!|
|Debian        |​Squeeze Backports|0.3.11   |Fundamentally broken - do not use|
|Debian        |​Wheezy   |0.3.11           |Fundamentally broken - do not use|
|Debian        |​Wheezy-backports|0.14.10   |Awful: 23 stable updates missing! version no longer supported, known bugs including crashes and vulnerabilities - avoid!|
|Debian        |​Jessie   |0.14.10	   |Awful: 23 stable updates missing! version no longer supported, known bugs including crashes and vulnerabilities - avoid!|
|Debian        |​Jessie-backports|0.16.3    |Not too bad|
|Gentoo        |​Stable   |0.15.6           |Not too bad: 4 minor updates behind|
|Gentoo        |​Testing  |​0.15.9           |Good: only one minor update behind|
|​Arch          |n/a      |​0.15.9           |Good: only one minor update behind|
</details>