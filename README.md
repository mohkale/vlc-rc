# vlc-rc

VLC remote control interface for emacs.

<pre>
        __
 _   __/ /____      __________
| | / / / ___/_____/ ___/ ___/
| |/ / / /__/_____/ /  / /__
|___/_/\___/     /_/   \___/

</pre>

This package adds support for controlling the [vlc media player](https://www.videolan.org/vlc/index.en-GB.html) from emacs using VLCs remote control interface.

## Quick Setup

Move vlc-rc.el to a location on your emacs load-path and require it `(require 'vlc-rc)`. You may want to customise:

* vlc-program-name, to the complete path to your VLC executeable if its not in your PATH variable.
* vlc-server-port, to the port on localhost where you often run VLCs remote control interface.
* vlc-response-check-interval, if you're running on a slow machine or have issues with vlc-rc responses.

I'd also suggest taking a look at the external integration functions, which provide support for vlc like tasks to other modes. For example: `(vlc/dired-add-file)` plays the file at point in a dired buffer using vlc.

## Keybindings

Keybindings for vlc-rc are bound in the `vlc-rc-map` which by default isn't bound to any key. You have to do this manually. For those running in spacemacs, I'd advise binding the map to 'SPC v' by doing:

```elisp
(use-package vlc-rc
  :config
  (spacemacs/set-leader-keys "v" vlc-rc-map))
```

if you're using pure emacs, you can bind the map to any key of your choosing with global-set-key.

For a list of all the available bindings, eval: `(describe-keymap)` and search for vlc-rc-map.

## Features

As of now, you can use vlc-rc to:

* to start or kill a vlc remote controlled process.
* pause or unpause running videos.
* add files to your playlist and move to the next or previous video.
* jump to arbitrary videos in your playlist
* take snapshots/screengrabs of videos.
* control the volume of playback.
* start or stop playback (not the same as pausing running videos).
* set your position (in seconds) for the currently playing video.
* manipulate the speed of playback.
* toggle looping, repeating, shuffling and fullscreen.
* set the audio device, channel & track.
* set the video crop, aspect ration, zoom or subtitle track.

Functionality which will hopefully be coming soon is:
* sending arbitrary keybindings to vlc.
* binding emacs to an open (non remote controlled) vlc instance.
* jumping to chapters or titles in a video stream.
* sending URLs or other input types as files for vlc to play.

You may find a more up to date version of this script on my [dotfiles](https://github.com/MoHKale/.dotfiles) repo; I'll try to keep them synced, but that's were experimental changes will be placed.
