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
