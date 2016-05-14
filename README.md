PID Cat
=======

An update to Jake Wharton's [update][4] to Jeff Sharkey's excellent [logcat color script][1]
which supports `adb`'s arguments and filter specs, as well as filtering
log entries for processes from a specific application package.

During application development you often want to only display log messages
coming from your app. Unfortunately, because the process ID changes every time
you deploy to the phone it becomes a challenge to grep for the right thing.

This script solves that problem by filtering by application package. Supply the
target package as an optional argument to the python script and enjoy a more
convenient development process.

    pidcat --package com.oprah.bees.android *:S AndroidRuntime:E


Here is an example of the output when running for the Google Plus app:

![Example screen](screen.png)


Install
-------

Get the script:

 * Any platform: Download the `pidcat.py` and place it on your PATH.


Make sure that `adb` from the [Android SDK][3] is on your PATH. This script will
not work unless this is that case. That means, when you type `adb` and press
enter into your terminal something actually happens.

To include `adb` and other android tools on your path:

    export PATH=$PATH:<path to Android SDK>/platform-tools
    export PATH=$PATH:<path to Android SDK>/tools

Include these lines in your `.bashrc` or `.zshrc`.

*Note:* `<path to Android SDK>` should be absolute and not relative.

 [1]: http://jsharkey.org/blog/2009/04/22/modifying-the-android-logcat-stream-for-full-color-debugging/
 [2]: http://brew.sh
 [3]: http://developer.android.com/sdk/
 [4]: https://github.com/JakeWharton/pidcat
