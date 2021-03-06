# x11docker/trinity

Trinity desktop environment based on Debian. Trinity is the successor of KDE 3. 
 - Run Trinity desktop in Docker.
 - Use [x11docker](https://github.com/mviereck/x11docker) to run GUI applications and desktop environments in docker images. 

# Command examples: 
 - Single application: `x11docker x11docker/trinity konquerer`
 - Full desktop: `x11docker --desktop x11docker/trinity`

# Options:
 - Persistent home folder stored on host with   `--home`
 - Shared host file or folder with              `--share PATH`
 - Hardware acceleration with option            `--gpu`
 - Clipboard sharing with option                `--clipboard`
 - ALSA sound support with option               `--alsa`
 - Pulseaudio sound support with option         `--pulseaudio`
 - Language locale settings with                `--lang [=$LANG]`
 - Printing over CUPS with                      `--printer`
 - Webcam support with                          `--webcam`

Look at `x11docker --help` for further options.
 
# Extend base image
This image contains a lot of standard applications; more are available in [Trinity repository](http://ftp.fau.de/trinity/trinity-r14.0.0/debian/pool/main/). 
To add further desired applications, create your own Dockerfile based on `x11docker/trinity`. 
Example:
```
# Trinity with kaffeine, vlc and pulseaudio
FROM x11docker/trinity
RUN apt-get update
RUN apt-get install -y kaffeine-trinity vlc libpulse0
```

# Screenshot
Trinity desktop in a Weston window running with x11docker:
 
![screenshot](https://raw.githubusercontent.com/mviereck/x11docker/screenshots/screenshot-trinity.png "Trinity desktop running in Weston window using x11docker")
