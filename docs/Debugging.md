![Bugs](https://xpra.org/icons/bugs.png)

# First Steps
For capturing the data required for [filing bug reports](../issues/new/choose), you can use the bug reporting tool which is available from most dialog screens and from the system tray menu - it takes care of collecting a lot of the information required for bugs reports.
The _session info_ dialog window is also useful for diagnostics.

Always try to narrow it down as much as possible, by turning off as many features as possible (clipboard, audio, OpenGL, etc) and trying various [encodings](../docs/Usage/Encodings).\
If possible, try another [operating system](./Platforms) or another client (ie: the [builtin HTML5 client](https://github.com/Xpra-org/xpra-html5)), try a different version, etc

`xpra info` is always good to have.

The `xpra toolbox`, which is also accessible from the main launch screen, can be used both natively on the client or through an xpra session on the server. The test tools from this toolbox should run pretty much the same in both cases, comparing the results can be useful.

[Debug Logging](https://github.com/Xpra-org/xpra/blob/master/docs/Usage/Logging.md) is the most commonly used debugging technique, enable logging for the subsystem categories relevant to your problem.


# Domain specific debugging
Some areas of the system may have dedicated pages which may be more useful for debugging:
* [keyboard](../docs/Features/Keyboard)
* [encodings](../docs/Usage/Encodings)


# GDB
When dealing with crashes ("core dumped"), the best way to debug is to fire gdb to get a backtrace.

## Attaching to an existing xpra process
Find the `pid` of the xpra process with:
```
ps -ef | grep xpra
```
Then attach gdb to this process:
```
gdb python $PID_OF_XPRA_PROCESS_TO_DEBUG
```
wait for it to load all the debug symbols then:
```
(gdb) continue
```
## Starting xpra in gdb
```
gdb /usr/bin/python3
run /usr/bin/xpra start ...
```
or simply:
```
gdb --args /usr/bin/python /usr/bin/xpra start ...
run
```
## Getting the backtrace
Then once you manage to hit the crash, gdb should show you its prompt again and you can extract the python stacktrace with `py-bt` and the full stacktrace with `bt`. Having both is useful.

Note: installing the required "`debug`" symbol packages for your distribution is out of scope, please refer to your vendor's package manager for details (ie: [debian](http://wiki.debian.org/HowToGetABacktrace) and [yum debuginfo-install](http://yum.baseurl.org/wiki/YumUtils/DebugInfoInstall)).

## Signal Handling
Xpra handles `SIGINT`, `SIGTERM` and `SIGUSR1` + `SIGUSR2`.

To prevent gdb from intercepting `SIGINT` so you can send this signal to the xpra process, use `handle SIGINT nostop pass`. ie:
```
gdb -ex "handle SIGINT nostop pass" \
--args /usr/bin/python3 /usr/bin/xpra start :20 --no-daemon --start=xterm
```
