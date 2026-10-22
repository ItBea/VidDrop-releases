# VidDrop

A simple Mac app for downloading videos and audio from websites. Paste a link, choose a format, press Download. It's a friendly window around the open-source tools [yt-dlp](https://github.com/yt-dlp/yt-dlp) and [FFmpeg](https://ffmpeg.org).

### [⬇ Download VidDrop (.dmg)](https://github.com/ItBea/VidDrop-releases/releases/latest/download/VidDrop.dmg)

## What it does

- Downloads **video** (mp4, mkv, webm) or **audio** (mp3, m4a, wav, flac, opus) at the quality you pick
- **Trim** a video to a time range, with a preview, before downloading
- Saves a video's **thumbnail** — alongside the video, or on its own — and a still **frame** from the trim window
- **Playlists** show as one group, with what's downloading, finished and still queued
- Converts files you already have to other formats
- Updates itself (see below)

## Requirements

- A Mac with **Apple silicon** (M1 or later)
- **macOS 26.3** or later

## Installing

1. Download **VidDrop.dmg** using the link above and open it.
2. Drag **VidDrop (Beta)** onto the **Applications** folder. Keep it there — that's what lets it update itself.
3. Open it from Applications. The first time, macOS will refuse, because VidDrop isn't notarized by Apple. This is a one-time step:
   - Open **System Settings → Privacy & Security** and scroll down to the **Security** section.
   - Find the message about "VidDrop (Beta)" and click **Open Anyway**, then enter your Mac password.

   Or, in Terminal: `xattr -dr com.apple.quarantine "/Applications/VidDrop (Beta).app"`

## Updates

- VidDrop checks this page for new versions about once a day. When there is one, a window offers **Update Now**, **Later** or **Skip This Version**. You can also check any time from the **VidDrop** menu → **Check for App Updates…**
- Every update is cryptographically signed, and VidDrop refuses any that isn't.
- The download tools (yt-dlp, FFmpeg, gallery-dl) update separately, through the small banner at the top of the window.

See [Releases](https://github.com/ItBea/VidDrop-releases/releases) for what changed in each version.

## Sites that need you to be logged in

Some sites only let signed-in people download. Sign in to the site in your web browser, then in VidDrop open **Settings → Browser Cookies** and pick that browser. If a download fails and a login might be the reason, VidDrop says so. (Safari needs Full Disk Access; Chrome and Brave may ask for your Mac password.)

## Privacy

VidDrop has no accounts, analytics or tracking of its own. It contacts GitHub (to check for updates), PyPI and the FFmpeg builds site (to keep the download tools current), and — when you download something — the site you asked it to download from. If you choose a browser under Browser Cookies, VidDrop lets yt-dlp read that browser's cookies, only for the sites you ask it to download from.

## Use it responsibly

Only download things you have the right to, and follow each site's terms.

## Open-source software inside VidDrop

VidDrop includes these separate programs, each under its own licence. They are not modified.

| Component | Licence | Source |
|---|---|---|
| yt-dlp | Unlicense | https://github.com/yt-dlp/yt-dlp |
| gallery-dl | GPL-2.0-only | https://github.com/mikf/gallery-dl |
| FFmpeg (static build by Martin Riedl, configured with `--enable-gpl --enable-version3`, i.e. GPL v3) | GPL-3.0-or-later | https://ffmpeg.org · builds and build details: https://ffmpeg.martin-riedl.de |
| Deno | MIT | https://github.com/denoland/deno |
| Python | PSF License | https://www.python.org |
| Sparkle (the updater) | MIT | https://github.com/sparkle-project/Sparkle |

Each of these comes with further libraries under their own licences; see the projects above.
