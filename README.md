# firefox-ctrl-q-workaround
A workaround for Firefox 57 Quantum breaking CtrlQ Disable Extensions on Linux

# How to use
Bind the script to Ctrl+Q system wide. For example, I use i3wm, so I have this in my i3 config

```
bindsym Control+q exec ~/noctrlq.sh
```

You might need to install `xdotool` and `xvkbd`.

# How it works
I gets the active window using xdotool and if it's not Firefox, it uses xvkbd to forward the Ctrl+Q onto it, otherwise it is Firefox and it doesn't. Much thank to this StackOverflow question: https://askubuntu.com/questions/97213/application-specific-key-combination-remapping

# Why the fuck?
The geniuses over at Mozilla broke every single method of turning off Ctrl+Q to quit in Firefox on Linux when they released 57/Quantum. There is a Ctrl+Q bypass addon written in WebExtensions, but a bug exists in the Linux version of Firefox that makes that addon not work (only works on macOS (╯°□°）╯︵ ┻━┻) and has been unfixed for literally fucking months. 
