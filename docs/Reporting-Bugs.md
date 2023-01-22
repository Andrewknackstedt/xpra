![Bugs](https://xpra.org/icons/bugs.png)

# Recommended reading
If you have not read it yet, please take a moment to skim through [Smart Questions](http://www.catb.org/esr/faqs/smart-questions.html#beprecise) - it is a very good read and will be helpful to you well beyond the scope of this project.

Please consider using the builtin bug reporting tool which can be accessed from the system tray menu, using the `Alt+Shift+F3` key shortcut, or launched separately using the subcommand: `xpra bug-report`. On MS Windows, you can also run `Bug_Report.exe`.

# Generic guidelines
Here is some information which is often relevant and should therefore be included in most tickets to save time:
* what operating system is used on both the client and server, including the full version details
* changes made to the default configuration, if any. This can be shown with the command: `xpra showconfig`
* the desktop environment, window manager used - if applicable
* anything that would make the setup unusual: number of screens, resolution, virtualization software, access via another remote desktop tool (`VNC`, `RDP`, ..), etc
* the network setup, bandwidth constraints (ie: local, `LAN` or `DSL`)
* the full command lines used both on the server and client
* the server log file, or output if no log file is used
* the environment, ie: `%PATH%` on MS Windows, `$PATH` and `$LD_LIBRARY_PATH` on Linux, etc
* `xpra info` for the session
* how the software was installed and what version, in full
* is this a new problem or a regression? if this is a regression, when did it start?
* are there other bugs that are similar?
* are there other unusual issues / behaviour apart from this particular bug?
* is it reproducible reliably? and if so, how?
* does this happen with all picture encodings?
* does switching off certain features make a difference (ie: sound, opengl, clipboard)
* include relevant parts of the log files - including enough context to investigate (not just the last line showing the error message, but not necessarily the whole log file either)
* does re-connecting help?
* does it happen with other type of clients (different OS, etc)
* if possible, follow the [debugging instructions](./Debugging)
* [please don't use pastebins](http://who-t.blogspot.com/2016/12/please-dont-use-pastebins-in-bugs.html)

The best way to ensure that the information is clear and detailed is often to just paste the command lines used to get the information directly. ie: rather than saying "I have the latest version installed" (which by definition, changes all the time, varies depending the platform, architecture, distribution channel), paste something like this:
```
    $ rpm -qa | grep xpra
    xpra-4.0.6-10.fc33.x86_64
```
Obviously, the type of information needed varies depending on the type of bug - see [keyboard bugs](https://github.com/Xpra-org/xpra/blob/master/docs/Features/Keyboard.md) for example.
