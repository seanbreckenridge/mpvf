# mpvf

<img src="https://raw.githubusercontent.com/seanbreckenridge/mpvf/master/.github/demo.gif">

Interface to select a `youtube-dl` format for streaming [stuff](https://ytdl-org.github.io/youtube-dl/supportedsites.html) with `mpv`.

If you select a format with video only, automatically adds 'bestaudio' to the format.

```
Usage: mpvf URL [OPTION]...

Pass the URL to stream from as the first argument.
Additional options/arguments are passed onto mpv.
```

You can set the `MPVF_PICKER` environment variable to use `dmenu`/`rofi` instead of `fzf`:

```
export MPVF_PICKER=rofi
mpvf "<URL>"
export MPVF_PICKER=dmenu
mpvf "<URL>"
```

### Installation

Install each dependency if not already installed and then copy `mpvf` to somewhere on your path.

Dependencies: [`mpv`](https://mpv.io/), [`youtube-dl`](https://ytdl-org.github.io/youtube-dl/index.html), [`fzf`](https://github.com/junegunn/fzf) (or specify `dmenu`/`rofi` as alternative)

### Notes

If you want to stream just the audio, you can select the audio format, or pass the `--no-video` `mpv` flag.

I've *further* wrapped this script as well:

* bound to different keybinds:
  * [grab URL from my clipboard and stream using `mpvf`](https://sean.fish/d/stream-media?dark)
  * or, grab the URL and [just stream audio](https://sean.fish/d/stream-audio?dark)
  * or, grab the URL and [stream video](https://sean.fish/d/stream-corner?dark), stickying the video in the bottom right of the screen ('picture in picture'-like), using [this](https://sean.fish/d/i3-picture-in-picture?dark)
* [`twitch`](https://sean.fish/d/twitch?dark): streams a twitch stream using `mpvf`. See [this blog post](https://exobrain.sean.fish/post/how_i/watch_twitch/) for more context.
* [`mediaproxyvideo`](https://github.com/seanbreckenridge/vps/blob/master/mediaproxyvideo): mostly a copy of `mpvf`, which prompts me to select a format, `ssh`'s onto my server, `youtube-dl`/`ffmpeg`'s that video onto my server, and copies the public link its hosted on onto my clipboard.
