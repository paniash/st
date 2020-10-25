# Ashish's build of st
st is a simple terminal emulator for X which sucks less. This build has additional features which make it even better!

## Requirements
In order to build st you need the Xlib header files.

## Features
+ **zoom/change font size**: same bindings as above, but holding down shift as well. `alt-shift-home` returns to default
+ **copy text** with `alt-c`, **paste** is `alt-v` or `shift-insert`

## Patches
- Alpha - Provides transparency to st (requires a compositor like picom)
- Anysize - Terminal programs do not scale very well with the terminal emulator itself. This patch takes care of it.
- Clipboard - Copy and paste within st or to/from external programs like a web browser.
- Newterm - Opens a new instance of st with the current working directory.
- Boxdraw - Render line drawings even better (instead of badly pixelated ones from the prehistoric era).

## Installation
Edit config.mk to match your local setup (st is installed into
the `/usr/local` namespace by default).

```sh
git clone https://github.com/paniash/st
cd st
sudo make clean install
```

## Running st
If you did not install st with `make clean install`, you must compile
the st terminfo entry with the following command:

```sh
tic -sx st.info
```

See the man page for additional details.

### Colors
The best colorscheme, [gruvbox!](https://github.com/morhetz/gruvbox)

## Notes on Emojis and Special Characters
If st crashes when viewing emojis, install [libxft-bgra](https://aur.archlinux.org/packages/libxft-bgra/) from the AUR.

## TODO
- Add scrollback (breaks vim buffer when used with vifm).
- Copy/follow links

### Contributions
You are more than welcome to fork this repo and make a PR to contribute.
