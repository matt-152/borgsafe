# borgsafe

Usage: borgsafe repo::archive [--] COMMAND

Env Vars:
- BORG\_PASSPHRASE: used when unlocking the targeted archive
- Other borg environment variables should work if exported (man borg >
  Environment Variables)

Minimal utility using borg as an encrypted filesystem. It's certainly "minimal"
(not a finished product), but sophisticated enough I'd feel guilty for not
sharing it (and would regret losing it). Developed on OS X, unsure of
compatability with other *nix-es.

The script extracts a borg archive into a temporary directory. It treats all of
its arguments following the archive as a command to your preferred $SHELL,
running at the root of this directory. When the command is done running, it will
save any changes made to the files. 

The script sets restrictive permissions on this directory to try and protect
against snooping, but I'm unsure how secure this actually is in practice.
