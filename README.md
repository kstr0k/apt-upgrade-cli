# apt upgrade CLI

Lightweight front-end to selectively upgrade packages on Debian. Started as a workaround for `apt upgrade`'s refusal to take a list of packages as arguments. Manually-installed status (`apt-mark`) is preserved -- packages remain autoremovable if they were so before.

## Copyright

`Alin Mr <almr.oss@outlook.com>` / MIT license

## Usage

With no package arguments, brings up a `dialog` CLI to select upgradable packages (none marked by default, or all with --all). With `-e`, calls `$EDITOR` to pick from `apt list --upgradable` output (which includes old / new `dpkg` versions.)

See `--help`.
