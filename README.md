# Not Strict Paredit

Subset of Emacs Paredit-like Structural editing and navigation for Common Lisp, Clojure, Fennel, Janet and Scheme.

This is a [Paredit](http://mumble.net/~campbell/emacs/paredit.el) extension for [Visual Studio Code](https://code.visualstudio.com).  It is a thin wrapper around [paredit.js](http://robert.kra.hn/projects/paredit-js).

This is a fork of [Strict Paredit](https://github.com/ailisp/strict-paredit-vscode) including the following changes:

* Not strict by default
* Remove and tweak some keybindings
* Support for Fennel and Janet
* Update dependencies

N.B. The default state has very few key bindings because:

* I don't use most of paredit's commands
* The defaults completely ignore some common conventions

## Commands

Note: You can choose to disable all default key bindings by configuring `paredit.defaultKeyMap` to `none`. (Then you probably also want to register your own shortcuts for the commands you often use. see `etc/keys.json` for example). By default the strict mode map is not used. Below commands work in both strict mode and original mode.

Note: Apparently, it is necessary to write bindings like "ctrl+shift+0" instead of "ctrl+)" when specifying settings.  I don't do this below as it doesn't seem to aid memory at all, let alone help make a link with the original commands in Emacs.

### Navigation

Default keybinding | Action
------------------ | ------
ctrl+alt+f         | Forward Sexp
ctrl+alt+b         | Backward Sexp
ctrl+alt+d         | Forward Down Sexp
ctrl+alt+u         | Backward Up Sexp
None               | Close List

### Selecting

Default keybinding | Action
------------------ | ------
None               | Expand Selection
None               | Shrink Selection
None               | Select Current Top Level Form

### Editing

Default keybinding | Action
------------------ | ------
ctrl+)             | Slurp Forward
ctrl+(             | Slurp Backward
ctrl+}             | Barf Forward
ctrl+{             | Barf Backward
None               | Splice
None               | Split Sexp
ctrl+alt+k         | Kill Sexp Forward
None               | Kill Sexp Backward
None               | Splice & Kill Forward
None               | Splice & Kill Backward
None               | Wrap Around ()
None               | Wrap Around []
None               | Wrap Around {}
None               | Indent
ctrl+alt+t         | Transpose

## Strict only keybinding
Strict mode keybinding | Action
---------------------- | ------
None                   | Delete Backward or move left if at `)]}`
None                   | Delete Forward or move right if at `)]}`
None                   | Delete Forward or move right if at `)]}`
None                   | Force Delete Backward
None                   | Force Delete Forward
None                   | Force Delete Forward

NB: **Strict mode is disabled by default.** In strict mode, the backspace and delete keys won't let you remove parentheses or brackets so they become unbalanced. To force a delete anyway, use the supplied commands for that. Strict mode can be switched on/off by configuring `paredit.defaultKeyMap` to `strict`/`original`.


### Copying/Yanking

Default keybinding | Action
------------------ | ------
None               | Copy Forward Sexp
None               | Copy Backward Sexp
None               | Copy Forward Down Sexp
None               | Copy Backward Up Sexp
None               | Copy Close List

### Cutting

Default keybinding | Action
------------------ | ------
None               | Cut Forward Sexp
None               | Cut Backward Sexp
None               | Cut Forward Down Sexp
None               | Cut Backward Up Sexp
None               | Cut Close List
