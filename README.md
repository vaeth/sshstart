# sshstart

Start `ssh-agent`/`ssh-add` only when you really use __ssh__ or friends

(C) Martin Väth (martin at mvath.de).
This project is under the BSD license.

This script acts as a frontend for `ssh-add` and `ssh-agent` which asks you for
the passphrase automatically but only the first time you run __ssh__
and friends.

The `keychain` script from https://github.com/funtoo/keychain
is supported if it is available.
(A reasonable new version of that script is required.)

To install `sshstart` simply copy it into your `$PATH`.
You will want to set corresponding shell aliases in your shell:
To get a description run

`sshstart -h`

You also need `push.sh` from https://github.com/vaeth/push in your `$PATH`.

For Gentoo, there is an ebuild in the mv overlay (available over layman).
