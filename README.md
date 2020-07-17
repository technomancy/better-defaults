# Better Defaults for Emacs

This project is now
[hosted on sourcehut](https://git.sr.ht/~technomancy/better-defaults). To
contribute, please send patches to the author by email or by
contacting him on Freenode.

There are a number of unfortunate facts about the way Emacs works out
of the box. While all users will eventually need to learn to write
Emacs Lisp in order to customize it to their particular tastes, this
package attempts to address the most obvious of deficiencies in
uncontroversial ways that nearly everyone can agree upon.

Why not just fix Emacs? Suggesting a change to the defaults of Emacs
usually results in a long thread in which people who have been using
Emacs for decades loudly complain about how the change would be
disruptive to their habits and how it's just one line for people to
get the improved behaviour in their own config files. While I would
love to see each of these changes become part of Emacs, I don't hold a
lot of hope for it.

Obviously there are many further tweaks you could do to improve Emacs,
(like those the Starter Kit and similar packages) but this package
focuses a few changes that have near-universal appeal, lovingly
hand-selected by inhabitants of the `#emacs` channel on Freenode. The
approach of the Starter Kit and co. is problematic in that when users
add in a big pile of unrelated functionality it's difficult to debug
when it goes wrong, and it's hard to tell where a specific piece of
functionality came from if it turns out to be undesired.

## Usage

1. Clone this repository.
2. Add `(add-to-list 'load-path "/path/to/better-defaults")` to your init-file.
3. Add `(require 'better-defaults)` to your init-file.

## New behaviour

* `ido-mode` allows many operations (like buffer switching and file
  navigation) to be enhanced with instant feedback among the
  completion choices. If you like ido, you should check out
  [ido-hacks](https://github.com/scottjad/ido-hacks) and
  [smex](https://github.com/nonsequitur/smex). Sometimes when creating
  a new file you'll want to temporarily disable ido; this can be done
  with `C-f`. You may also want to look at
  [`ido-use-virtual-buffers`](http://www.archivum.info/emacs-devel@gnu.org/2010-04/00629/ChangeLog-entry-for-ido.el.html).

* The toolbar, menu bar, and scroll bar are all turned off.

* The `uniquify` library makes it so that when you visit two files
  with the same name in different directories, the buffer names have
  the directory name appended to them instead of the silly `hello<2>`
  names you get by default.

* The `saveplace` library saves the location of the point when you
  kill a buffer and returns to it next time you visit the associated file.

* A few key bindings are replaced with more powerful equivalents:
  `M-/` is `hippie-expand` instead of `dabbrev-expand`, `C-x C-b` is
  `ibuffer` instead of `list-buffers`, and `C-s` and `C-r` are
  swapped with regex-aware incremental search functions.

* `show-paren-mode` highlights the matching pair when the point is
  over parentheses.

* Under X, killing and yanking uses the X clipboard rather than just
  the primary selection.

* Apropos commands perform more extensive searches than default.

* Mouse yanking inserts at the point instead of the location of the click.

* Backups are stored inside `user-emacs-directory`. (Usually `~/.emacs.d`)

* `M-z` (formerly `zap-to-char`) is replaced with the far more useful
  `zap-up-to-char`.

* `require-final-newline` is set to avoid problems with crontabs, etc.

* Setting `load-prefer-newer` prevents stale elisp bytecode from shadowing more up-to-date source files.

* Ediff is set up to use the existing frame instead of creating a new one.

* `indent-tabs-mode` defaults to nil.

## Copyright

Copyright © 2013-2014 Phil Hagelberg and contributors

Licensed under the same license as Emacs (GPL v3 or later) unless otherwise specified.
