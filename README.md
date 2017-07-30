﻿GTK3-mushrooms
===

This is a set of patches for GTK3 library that makes it better for me and maybe for you too. ;-) I haven't wide knowledge about programming in C, so quality of this patches can be not good. But it works! See list of patches below.

This package is based on official GTK3 package from Arch Linux. In my version library is compiled without Broadway backend, documentation and example applications. Using this package with GNOME desktop is not recommended. It's for classic GTK-based environments like MATE or XFCE.

Client Side Decorations
---

* CSDs are totally disabled by default. All windows are decorated only by window manager. You can enable CSDs by setting `GTK_CSD=0` environment variable (or `GTK_CSD=1` to force CSDs on each GTK3 window).
* Client side shadows of windows, menus and tooltips are disabled by default. You can enable shadows by setting `GTK_CSD=1` environment variable.
* Window title and subtitle are removed from headerbar. Subtitle is added to native titlebar.
* Minimize, maximize and close buttons are removed. Application menu button has changed icon.

File chooser
---

* Annoying single-click "feature" in file list is disabled. You always have to double-click to choose file from list. See https://bugzilla.gnome.org/show_bug.cgi?id=758065.
* Typeahead feature is restored. Recursive file search will not be ran when you start typing. See https://bugzilla.gnome.org/show_bug.cgi?id=784029.
* Current working directory is opened by default instead of section with recently used files.
* "Other locations" button is removed from places sidebar. All mounted devices and drives are accessible directly.
* File system button in places sidebar is labeled as "File System" instead of "Computer".
* Trash and XDG user directories (like Pictures, Downloads, Documents) are removed from places sidebar. They can be added as bookmarks.

Print dialog
---

* Appearance of print dialog is less "gnomish" (natural margins are restored).
* Atril instead of Evince is set as default previewer.

Icons
---

* Some of GTK stock icons on buttons are restored. You can see it in GTK internal dialogs and in some applications.
* Context menus of text fields, links and labels have restored icons too.
* Colorized icons instead of symbolic icons are used in file chooser dialog.

Popovers
---

* File chooser dialog, places sidebar and color chooser dialog use classic menu as context menu instead of popover.
* Menus of menu buttons are displayed as classic menu instead of popover.

Others
---

* Status bars are smaller regardless of used theme.
* Scrollbars are always visible. Environment variable is not needed.
* Delay before showing mnemonics is removed. You don't have to wait when you press Left Alt button.
* Integration with Accessibility Toolkit is disabled by default to avoid errors in console output. See https://unix.stackexchange.com/questions/230238. **Important: if you are using assistive technologies (such as Orca reader) you must restore default GTK behavior by setting `NO_AT_BRIDGE=0` environment variable.**

Themes
---

* Default Adwaita theme and its dark variant have smaller controls (buttons, fields, tabs, etc.).
* HighContrast themes also have reduced controls (testing).

--------

Credits
---

* https://launchpad.net/~gnome3-team — file chooser single-click patch.
* https://aur.archlinux.org/packages/gtk3-typeahead — file chooser typeahead patch.
