## jlink-accept-license
##### Shell script to automatically accept J-Link terms of use

I occassionally find myself wanting to use my J-Link remotely via SSH. But if it is the first time running one of the tools (e.g., `gdbserver`) for the day, a dialog box is presented on my X11 display which I cannot see. This script uses [`xdotool`](https://github.com/jordansissel/xdotool) to locate that dialog, check the "do not hassle me" checkbox, and click the "Accept" button.
