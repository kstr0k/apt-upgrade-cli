# apt upgrade CLI

Lightweight front-end to selectively upgrade packages on Debian. Started as a workaround for `apt upgrade`'s refusal to take a list of packages as arguments. Manually-installed status (`apt-mark`) is preserved &mdash; packages remain autoremovable if they were so before.

## Usage

All arguments are optional. `aptup` calls `$APTUP_EDITOR` or `$EDITOR` to select upgradable packages as reported by `apt list --upgradable` (none selected by default, or all with `--all`). Commented lines (starting with `#`) are ignored. Uncomment, re-comment and/or delete lines as appropriate, then save and exit.

`--dialog` switches the front-end TUI to `dialog` (if installed). Package-name arguments filter upgradable packages to only those supplied (if none: all installed packages are checked).

Usage hints for `vim`:
* in normal mode, go to column 1 and type `<C-V>` to enter block-visual mode; by selecting and deleting (`x`) the initial `#`, you can easily uncomment ranges of lines.
* in `--all` mode, you can delete some lines matching a regex with `:g/PATTERN/d`, or some *non-matching* lines with `:v/PATTERN/d`. For example, use `security` as the PATTERN.

`aptup --help`:
```
Usage: aptup [OPTION]... [PKG]...

Options:
  -u, --update        run apt update first
  --all               pre-select all packages for update
  --dialog            use "dialog" as front-end
  --editor, -e        use editor as front-end (default)
  -o APT_KEY=VAL ..   configure apt

*Editor selection*
  aptup tries $APTUP_EDITOR, $EDITOR, Debian sensible-editor, nano, vim.
```

## Copyright

`Alin Mr <almr.oss@outlook.com>` / MIT license
