My Openbox Config
=================

My [Openbox](http://openbox.org/) configuration files.

I try to keep things very minimal, with almost nothing but my windows on screen
(not even a desktop background) and just using Openbox's features, not adding a
lot of docks, panels, icons etc. Not even a desktop wallpaper. This minimalism
is what I like about Openbox - there's less to distract me and there's also
less to configure and manage and less to go wrong.

But I do add a handful of essentials, including a notifications daemon, a
system tray, an application launcher and an Openbox theme, and my own
Openbox configuration with my own keyboard shortcuts.

Requirements
------------

* Openbox (tested using Openbox 3.6.1 installed from the Ubuntu 16.10 package
  repositories).

* Runs `unity-settings-daemon` on login. This assumes you're using Ubuntu,
  and it makes a whole bunch of stuff just work.

* [Dunst](https://dunst-project.org/) notification daemon
  (`sudo apt install dunst` on Ubuntu)

* [Stalonetray](http://stalonetray.sourceforge.net/) system tray
  (`sudo apt install stalonetray`)

* [Rofi](https://github.com/DaveDavenport/rofi) application launcher
  (`sudo apt install rofi`)

* [tdc](https://github.com/MTecknology/tdc) (`sudo apt install tdc`)

* [Arc Openbox theme](https://github.com/dglava/arc-openbox)

  Also recommended: Arc GTK theme (`sudo apt install arc-theme`) and
  [Obsidian icon theme](https://github.com/madmaxms/iconpack-obsidian).
  You'll need Gnome Tweaks (`sudo apt install gnome-tweak-tool`) to activate
  these.

* Futura Bk BT font.

Default apps that are used by the menus and keyboard shortcuts (you can
easily change these):

* Gnome Terminal
* gVim
* Firefox
* Chrome
* Nautilus file manager
* Thunderbird email
* Gedit
* Gnome System Monitor

Installation
------------

On Ubuntu:

```bash
$ git clone https://github.com/seanh/openbox.git ~/.config/openbox
$ sudo apt install openbox dunst stalonetray rofi tdc
$ ln -s ~/.config/openbox/dunst ~/.config/
```

Logout, and login selecting the openbox session.

Usage
-----

### Keyboard shortcuts

#### Menus and launchers

* <kbd>Right Super</kbd>: show the root menu.

  Clicking the <kbd>Left Mouse Button</kbd> on an empty part of the desktop
  also shows this menu.

* <kbd>XF86Launch5</kbd>: show the client list combined menu (menu of all
  open windows on all desktops).

  Clicking the <kbd>Right Mouse Button</kbd> on an empty part of the desktop
  also shows this menu.

* <kbd><kbd>Super</kbd>+<kbd>Space</kbd></kbd>: show the client menu.

  This is the menu attached to the current window containing actions like
  minimizing and maximizing the window etc.

  There are also keyboard shortcuts for most of the actions in this menu,
  see below.

  Clicking on a window's title bar with the <kbd>Right Mouse Button</kbd> also
  shows this menu.

* <kbd><kbd>Super</kbd>+<kbd>t</kbd></kbd>: open a new terminal window.

* <kbd><kbd>Super</kbd>+<kbd>i</kbd></kbd>: open a new file manager window.

* <kbd><kbd>Super</kbd>+<kbd>p</kbd></kbd>: open the application launcher
  (rofi).

* <kbd><kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>Delete</kbd></kbd>: open the
  system monitor.

* <kbd>Print Screen</kbd>: take a screenshot.

#### Changing focused window

* <kbd><kbd>Alt</kbd>+<kbd>j</kbd></kbd> and <kbd><kbd>Alt</kbd>+<kbd>k</kbd></kbd>:
  switch to next or previous window.
  (<kbd><kbd>Alt</kbd>+<kbd>Tab</kbd></kbd> and
  <kbd><kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>Tab</kbd></kbd> also work.)

* <kbd><kbd>Super</kbd>+<kbd>&larr;</kbd>, <kbd>&rarr;</kbd>, <kbd>&uarr;</kbd> or <kbd>&darr;</kbd></kbd>:
  change focus to the nearest window to the left, right, top or bottom of the
  current window.

#### Moving windows

* <kbd><kbd>Super</kbd>+<kbd>m</kbd></kbd>: begin moving the current window
  with the keyboard. When in move mode use the arrow keys to move the window,
  and hit <kbd>Enter</kbd> to exit move mode.

  <kbd><kbd>Shift</kbd>+<kbd>&larr;</kbd>, <kbd>&rarr;</kbd>, <kbd>&uarr;</kbd> or <kbd>&darr;</kbd></kbd> while in move mode will
  jump the window all the way to the left, right, top or bottom screen edge.

  Moving the mouse while in move mode will also move the window.

  <kbd>Escape</kbd> cancels the move, putting the window back where it
  started.

  You can also pseudo-modally move the current window using the keyboard with
  <kbd><kbd>Shift</kbd>+<kbd>Super</kbd>+<kbd>&larr;</kbd>, <kbd>&rarr;</kbd>, <kbd>&uarr;</kbd> or <kbd>&darr;</kbd></kbd>.

  To move a window with the mouse just click and drag on its title bar using
  the <kbd>Left Mouse Button</kbd> _or_
  hold down <kbd>Super</kbd> and click and drag anywhere on the window with
  the <kbd>Left Mouse Button</kbd>.

#### Resizing windows

* <kbd><kbd>Super</kbd>+<kbd>x</kbd></kbd>: maximize/restore the current
  window.

* <kbd><kbd>Super</kbd>+<kbd>z</kbd></kbd>: begin resizing the current window
  with the keyboard. Works similarly to moving a window with the keyboard,
  including mouse support and <kbd>Escape</kbd> to cancel the resize.

  You can also pseudo-modally resize the current window from its left and
  bottom edges:

  * <kbd><kbd>Alt</kbd>+<kbd>Super</kbd>+<kbd>&rarr;</kbd></kbd>: increase
    the width of the current window by extending its right edge.

  * <kbd><kbd>Alt</kbd>+<kbd>Super</kbd>+<kbd>&larr;</kbd></kbd>: decrease
    the width of the current window by retracting its right edge.

  * <kbd><kbd>Alt</kbd>+<kbd>Super</kbd>+<kbd>&darr;</kbd></kbd>: increase
    the height of the current window by extending its bottom edge.

  * <kbd><kbd>Alt</kbd>+<kbd>Super</kbd>+<kbd>&uarr;</kbd></kbd>: decrease
    the height of the current window by retracting its bottom edge.

  You can resize a window with the mouse by clicking and dragging from its
  edges and corners but many Openbox themes (including the Arc one that I
  use) make this click target very tiny so alternatively you can hold down
  <kbd>Super</kbd> and click-and-drag anywhere on the window using the
  <kbd>Right Mouse Button</kbd> to resize it.

* <kbd><kbd>Super</kbd>+<kbd>Page Up</kbd></kbd>: grow the window by extending
  its top edge upwards as far as the nearest other edge.

  This will grow the window upwards until it hits the bottom or top of another
  window or it hits the top screen edge. You can then hit
  <kbd><kbd>Super</kbd>+<kbd>Page Up</kbd></kbd> again to continue growing to
  the next edge.

  Once the top edge of the window hits the top of the screen, if you keep
  hitting <kbd><kbd>Super</kbd>+<kbd>Page Up</kbd></kbd> it will start
  **shrinking** the window by **retracting** its bottom edge to the nearest
  other edge (or just retracting it by a fixed amount, if there are no other
  edges to hit, eventually making the window very short).

* <kbd><kbd>Super</kbd>+<kbd>Page Down</kbd></kbd>: grow the window by extending
  its **bottom** edge downwards to the nearest other edge.

* <kbd><kbd>Super</kbd>+<kbd>Home</kbd></kbd>: grow the window by extending
  its **left** edge leftwards to the nearest other edge.

* <kbd><kbd>Super</kbd>+<kbd>End</kbd></kbd>: grow the window by extending
  its **right** edge rightwards to the nearest other edge.

* <kbd><kbd>Super</kbd>+<kbd>Enter</kbd></kbd>: grow the window by extending
  **all four edges** to the next edge in each direction.

  This will grow the window to fill all available screen space without
  overlapping any other windows that it doesn't already overlap.

  You can keep hitting <kbd><kbd>Super</kbd>+<kbd>Enter</kbd></kbd> to
  make it continue and cover up other windows. Eventually you can effectively
  maximize a window like this, though unlike with maximize there's no way
  to unmaximize it this way.

  Moving a smaller window on top of a bigger window then hitting
  <kbd><kbd>Super</kbd>+<kbd>Enter</kbd></kbd> will resize the small window
  to the same size as the bigger one.

  Moving two windows into the left and right sides of the screen and
  hitting <kbd><kbd>Super</kbd>+<kbd>Enter</kbd></kbd> on each will size
  each one to fill one side of the screen (not necessarily equally sized,
  depends on how you position the windows before hitting
  <kbd><kbd>Super</kbd>+<kbd>Enter</kbd></kbd>). This can be used to tile
  any number of windows into any number of screen areas.

#### Other window actions

* <kbd><kbd>Super</kbd>+<kbd>b</kbd></kbd>: show/hide the current window's
  decorations (title bar and border).

* <kbd><kbd>Alt</kbd>+<kbd>F4</kbd></kbd> or <kbd><kbd>Super</kbd>+<kbd>c</kbd></kbd>:
  close the current window.

* <kbd><kbd>Alt</kbd>+<kbd>Escape</kbd></kbd>: move the current window below
  all other windows and change focus to the previously focused window.

* <kbd><kbd>Super</kbd>+<kbd>r</kbd></kbd>: roll/unroll the current window
  (when a window is rolled up only its title bar is visible).

  Also known as "shading"/unshading the window. Double-clicking on a window's
  title bar with the <kbd>Left Mouse Button</kbd> will also shade it,
  and single-clicking on a shaded window will unshade it.

* <kbd><kbd>Super</kbd>+<kbd>n</kbd></kbd>: iconify (minimize) the current
  window.

#### Desktops

* <kbd><kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>&rarr;</kbd></kbd> and
  <kbd><kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>&larr;</kbd></kbd>: go to next
  and previous desktop.

* <kbd><kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>&rarr;</kbd></kbd> and
  <kbd><kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>&larr;</kbd></kbd>: go to next
  and previous desktop, taking the current window with you.

  You can also just drag a window against the edge of the screen using the
  mouse and hold it there for a second to move to the desktop left or right
  with it.

* <kbd><kbd>Super</kbd>+<kbd>F1</kbd>, <kbd>F2</kbd>, <kbd>F3</kbd> or <kbd>F4</kbd></kbd>:
  go to desktop 1, 2, 3 or 4.

#### Misc

* <kbd><kbd>Super</kbd>+<kbd>d</kbd></kbd>: show the desktop (minimize all windows).
  Hit it again to restore all the windows.
