# borgsafe
Minimal utility using borg as an encrypted filesystem. It's certainly "minimal" (not a finished product), but sophisticated enough I'd feel guilty for not sharing it (and would regret losing it). Developed on OS X, unsure of compatability with other *nix-es.

The script extracts a borg archive into a temporary directory. It treats all of its arguments as a command to your preferred $SHELL, running at the root of this directory. When the command is done running, it will save any changes made to the files. The script sets restrictive permissions on this directory to try and protect against snooping, but I'm unsure how secure this actually is in practice.

The script will version any changes to the content, but deliberately ignores metadata. This behavior can be changed by editing the "curDirHash" function.

The target borg repo is set in a variable at the top of the script. The script produces timestamped archives; the prefix used is also set as a variable at the top of the script. These top-level parameters may also be set as environment variables externally.
