py3status
=========

py3status is an extensible i3status wrapper written in python

Documentation
=========
See the wiki for up to date documentation : https://github.com/ultrabug/py3status/wiki

Requirements
=========
You must set the `output_format` to `i3bar` in the general section of your i3status.conf:
::
    general {
        output_format = "i3bar"
    }

Installation (all users)
=========
py3status is available on pypi:
::
    $ pip install py3status

Installation (Gentoo users)
=========
Add the `ultrabug` overlay on layman:
::
    $ sudo layman -a ultrabug

Install py3status:
::
    $ sudo emerge -a py3status

Installation (Arch users)
=========
Thanks to @waaaaargh, py3status is present in the Arch User Repository using this URL:
::
    https://aur.archlinux.org/packages/py3status-git/

Usage
=========
In your i3 config file, simply change the `status_command` with:
::
    status_command py3status

Usually you have your own i3status configuration, just point to it:
::
    status_command py3status -c ~/.i3/i3status.conf

Options
=========
You can see the help of py3status by issuing `py3status -h`:
::
    -c I3STATUS_CONF  path to i3status config file
    -d                disable integrated transformations
    -i INCLUDE_PATH   user-based class include directory (default .i3/py3status)
    -n INTERVAL       update interval in seconds (default 1 sec)
    -t CACHE_TIMEOUT  default injection cache timeout in seconds (default 60 sec)

Control
=========
Just like i3status, you can force an update by sending a SIGUSR1 signal to py3status.
Note that this will also send a SIGUSR1 signal to i3status.
::
    killall -USR1 py3status
