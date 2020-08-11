# apt upgrade CLI

Workaround for `apt upgrade`'s refusal to take a list of packages as arguments. Manually-installed status (`apt-mark`) is never affected, so packages remain autoremovable if they were so before. With no package arguments, brings up a dialog CLI to select from upgradable packages (none marked by default, or all with --all). Also see `--help`.
