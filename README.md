# mpvf

<img src="https://raw.githubusercontent.com/seanbreckenridge/mpvf/master/.github/demo.gif">

Interface to select a `youtube-dl` format for streaming [stuff](https://ytdl-org.github.io/youtube-dl/supportedsites.html) with `mpv`.

If you select a format with video only, automatically adds 'bestaudio' to the format.

```
Usage: mpvf URL [OPTION]...
Interface to select a youtube-dl format for streaming stuff with mpv.

Pass the URL to stream from as the first argument.
Additional options/arguments are passed onto mpv.

You can set the MPVF_DL environment variable to download
the selected format code instead, like:
MPVF_DL=1 mpvf https://... [youtube-dl OPTION...]
```

You can set the `MPVF_PICKER` environment variable to use `dmenu`/`rofi` instead of `fzf`:

```bash
export MPVF_PICKER=rofi
mpvf 'https://...'
export MPVF_PICKER=dmenu
mpvf 'https://...'
```

### Installation

Dependencies: [`mpv`](https://mpv.io/), [`youtube-dl`](https://ytdl-org.github.io/youtube-dl/index.html), [`fzf`](https://github.com/junegunn/fzf) (or specify `dmenu`/`rofi` as alternative)

Install each dependency if not already installed and then download/copy `mpvf` to somewhere on your `$PATH`.

Can also use [`sinister`](https://github.com/jamesqo/sinister): `sh <(curl -sSL http://git.io/sinister) -u 'https://raw.githubusercontent.com/seanbreckenridge/mpvf/master/mpvf'` to automate the `curl`/`chmod`/`mv` instead.

### Notes

If you want to stream just the audio, you can select the audio format, or pass the `--no-video` `mpv` flag.

I've _further_ wrapped this script as well:

- bound to different keybinds:
  - [grab URL from my clipboard and stream using `mpvf`](https://sean.fish/d/stream-media?dark)
  - or, grab the URL and [just stream audio](https://sean.fish/d/stream-audio?dark)
  - or, grab the URL and [stream video](https://sean.fish/d/stream-corner?dark), stickying the video in the bottom right of the screen ('picture in picture'-like), using [this](https://sean.fish/d/i3-picture-in-picture?dark)
  - have other related variations; to grab the URL and [stream at different resolutions](https://github.com/seanbreckenridge/dotfiles/blob/9da260bd6610dbbe5ff90b6bea54cfba48bd505a/.config/shortcuts.toml#L509-L562), often called from my RSS reader
- [`twitch`](https://sean.fish/d/twitch?dark): streams a twitch stream using `mpvf`. See [this blog post](https://exobrain.sean.fish/post/how_i/watch_twitch/) for more context.
- [`mediaproxyvideo`](https://github.com/seanbreckenridge/vps/blob/master/mediaproxyvideo): mostly a copy of `mpvf`, which prompts me to select a format, `ssh`'s onto my server, `youtube-dl`/`ffmpeg`'s that video onto my server, and copies the public link its hosted on onto my clipboard.
