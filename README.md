## jlink-accept-license
##### Shell script to automatically accept J-Link terms of use

I occassionally need to use my J-Link remotely via SSH. If it is the first time running one of the tools (e.g., `JLinkGDBServer`) for the day, a EULA dialog box is presented on my X11 display which I cannot see or interact with. You must interactively agree to the terms in this dialog box before the J-Link software will run.

If you do not have X11-forwarding configured, or cannot/do not have X11 installed locally, this script will control the remote X11 session to dismiss that dialog box, allowing you to use the J-Link software.

## Details

This script uses [`xdotool`](https://github.com/jordansissel/xdotool) to locate the `J-Link <VERSION> - Terms of use` dialog, and
1. Check the "do not hassle me" checkbox,
2. Click the `Accept` button:

[![J-Link EULA](image/jlink-eula.png "Plz do not sue me")](image/jlink-eula.png)

## Usage
### Legally, I **forbid** all usage of this software.

If `DISPLAY` is undefined, it will `export DISPLAY=:0` by default.

If this is not correct, try setting your `DISPLAY` environment variable:
```
% DISPLAY=:1 jlink-accept-license
```

The script can operate in one of two modes:
#### 1. Keyboard mode (default)
- Run with `MOUSE=`, `MOUSE=0`, or do not specify `MOUSE` at all.
- Presses `Tab` key to navigate focus onto checkbox and `Space` key to select/check it.
- Uses keyboard shortcut `Alt+a` to press `Accept` button.
#### 2. Mouse mode
- Run with `MOUSE=1`, or anything non-zero.
- Clicks the checkbox using an `X`, `Y` position relative to the bottom-left corner of the dialog box.
  - Modify script variables `xleft`, `ybotm` to adjust these relative offsets.
- Still uses keyboard shortcut `Alt+a` to press `Accept` button.
