# sshstart

Start `gpg-agent`/`ssh-add` automatically when you use __ssh__ or friends.

(C) Martin Väth (martin at mvath.de).
This project is under the MIT license.

This script acts as a frontend for __ssh__ and friends which asks you for
the passphrase of keys automatically, running `gpg-agent` and `ssh-add`
if necessary (but usually only once).

## New project

Version 4.0 is a ***ground-up rewrite*** with different internals and usage.
For instance, instead of being based on the keychain script, this project now
completely relies on gpg-agent's functionality to replace ssh-agent.
Also the way it is supposed to be called has completely been thought over.

## Installation and Usage

To install `sshstart` simply copy `bin/*` somewhere into your `$PATH`
and use `ssh-wrap`, `rsync-wrap`, etc. instead of `ssh`, `rsync`, etc.
In order to set correct environment variables for non-wrapped commands, put
```
unset SSH_AGENT_PID
eval "`sshstart -e`"
```
in your shell startup file. It might also be convenient to put e.g.
```
alias ssh='ssh-wrap --'
alias rsync='rsync-wrap --'
...
```
in your shell startup file to let 'ssh' ask for your keys only once.

To get more help run `sshstart -h`.

For __zsh completion__ support also copy 'zsh/*` into a directory of
your zsh's `$fpath`.

You may also need `push.sh` from https://github.com/vaeth/push in your `$PATH`.

For Gentoo, there is an ebuild in the `mv` repository
(available by `app-select/eselect-repository` or `app-portage/layman`).
