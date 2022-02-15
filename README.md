## jlink-accept-license
##### Shell script to automatically accept J-Link terms of use

I occassionally need to use my J-Link remotely via SSH. If it is the first time running one of the tools (e.g., `JLinkGDBServer`) for the day, a dialog box is presented on my X11 display which I cannot see or interact with. 

This script uses [`xdotool`](https://github.com/jordansissel/xdotool) to locate the `J-Link <VERSION> - Terms of use` dialog, and
1. Check the "do not hassle me" checkbox,
2. Click the `Accept` button:

[![J-Link EULA](image/jlink-eula.png "Plz do not sue me")](image/jlink-eula.png)

## Usage
#### Legally, I **forbid** all usage of this software.

But, if you _hypothetically_ encountered a message like the following:

```
% jlink-accept-license
Error: Can't open display: (null)
Failed creating new xdo instance
```

Try setting your _hypothetical_ `DISPLAY` environment variable:
```
% DISPLAY=:0 jlink-accept-license
```
