![Ubuntu](https://xpra.org/icons/ubuntu.png)

The problems with [distribution packages](./Distribution-Packages) are well documented - not least of which shipping versions with serious security issues, but the spectrum of problems with the Ubuntu packages is so extreme that it deserves its own wiki page.

_TLDR_: use [official packages](./Download) from https://xpra.org/ and things should just work.

***

The number one support request on the bug tracker, mailing list and IRC channel is by far "_problems with the Ubuntu packages_", this is solved in 99% of cases by installing the official packages.

<br />

This list is by no means exhaustive, but it should be enough to understand why the Ubuntu packages should be avoided (some of those issues are seriously debilitating):
* [Why can't I start xpra on a remote host and connect to it?](https://lists.devloop.org.uk/pipermail/shifter-users/2019-December/002450.html) - Lubuntu 18.04
* [xpra ubuntu html5 server problems](https://superuser.com/questions/1199110/) : html5 client is missing (also: [I could not get the example html5 client working..](https://github.com/mviereck/x11docker/issues/204#issuecomment-574943308))
* tty permissions issues with [Xdummy](https://github.com/Xpra-org/xpra/blob/master/docs/Usage/Xdummy.md)
* [unable to start Xserver via ssh](https://bugs.launchpad.net/ubuntu/+source/xpra/+bug/1777753)
* serious: [Ubuntu login screen hangs after installing xpra](https://superuser.com/questions/1222706/ubuntu-login-screen-hangs-after-installing-xpra/1265430#1265430)
* [Ubuntu 16.04.2 cannot login after installing xpra](https://askubuntu.com/questions/930161/)
* [xpra version on ubuntu 16.04](https://askubuntu.com/questions/821199/) (compatibility problems)
* [clipboard not working](../issues/2580) with Ubuntu 18.04 server version `2.1.3-r17247`
* [Stopped working suddenly on Ubuntu 18.04](https://github.com/kaueraal/run_scaled/issues/21#issuecomment-481983390)
* [Chrome window can not be resized or moved](https://lists.devloop.org.uk/pipermail/shifter-users/2020-May/002578.html) (Ubuntu Focal)
* [Xdummy cannot be used in Xenial](https://bugs.launchpad.net/ubuntu/+source/xserver-xorg-video-dummy/+bug/1589447/comments/8)
* [Cannot get "Get started" to work](https://xpra.org/trac/ticket/1783#comment:5) (XUbuntu 16.04)
* [workaround for buggy Debian / Ubuntu patch](../commit/d5dcf13a137ca9d58cf18d1479661b514f79aea8)
* [#2190](../issues/2190) and [more packaging problems](../issues/2190)
* [proxy processes not closing correctly](https://github.com/Xpra-org/xpra/issues/3327#issuecomment-953431989)
* [let's encrypt ssl certificates broken](https://github.com/Xpra-org/xpra/issues/3323#issuecomment-951587226)

----

Some examples from IRC:
```
18:39 < flonash> hi there! I'm trying to setup xpra in a ubuntu 16.04 docker container,
      but the "start-desktop" command isn't available back then. What alternatives are there? Thanks so much for helping me with this!
19:52 < flonash> it was still giving v0.15.6 ..
      but it looks like the instructions in that link weren't as helpful as
      https://winswitch.org/downloads/debian-repository.html?dist_select=xenial which worked
19:53 < flonash> I'm now up and running!

18:54 < caffeineaddict> damn, default ubuntu version is `xpra v2.1.3-r17247M` ...
      brb upgrading that first
19:31 < caffeineaddict> <.< latest version of software makes it work ... who'da thunk
```

And many many more..


***


Then the usage examples they are using at https://help.ubuntu.com/community/Xpra are out of date and plain wrong - don't do this:
```
xpra start :7;DISPLAY=:7 firefox`
```
Do this instead:
```
xpra start :7 --start=firefox
```
