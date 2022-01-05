---
title: 'Youtube and MP3s'
date: 2022-1-5T11:51:41-05:00
tags: ['tech', 'youtube', 'mp3']
description: 'Download YouTube to MP3 Format for Offline Enjoyment'
---

YouTube, whether you love it or hate it, is a great source for music that you typically cannot find on Spotify or Apple Music. I am a big fan of ambient music, not only chilling out and falling asleep to, but also just to have playing in the background while I work. I don't work well when there is music with lyrics playing; I'm very easily distracted. Ambient music helps me to focus on the task at hand and is much more pleasing to me than typical music. There are a few good selections on Apple Music for "focus music" playlists that I enjoy as well.

I wanted a way to collect these tracks and mixes so I could have a permanent offline copy. I don't want to have to rely on a streaming service or even my own music services at home (Navidrome, Jellyfin, Plex, etc); I'd rather have an offline MP3 to play how I want. Relying on streaming services is never a good idea. For example, I've had a few albums that I LOVE simply disappear from Apple Music and Spotify because of some unknown reason. It could have been a license expired, some region BS (even though I'm in the US), or whatever, it doesn't matter. If you want music to be more permanent, never just disappear, and under your control, then we need to take a few steps back and do things the old school way: MP3s.

Here is my workflow of how I download YouTube "music" into an MP3 file for personal consumption. To be honest, I don't use YT-DLP a lot as I use a Docker container called [MeTube](https://github.com/alexta69/metube) for my web-UI frontend; it does everything a lot easier if you are able to run a Docker container. Bonus steps for doing some simple edits like condensing long mixes down to shorter times and add a fade-in and fade-out!

# Pre-Reqs

I recommend that you have the latest version of Python and install both the [YT-DLP](https://github.com/yt-dlp/yt-dlp) and [pydub](https://github.com/jiaaro/pydub) modules using pip. Finally, make sure that you have the latest version of [FFMPEG](https://ffmpeg.org/) installed.

# Download Using YT-DLP

The command and options below will download a YouTube video of your choice in the best audio format available, embed the metadata of the video and output a MP3 labeled as the video title into the current directory.

```
yt-dlp --embed-thumbnail --embed-metadata --add-metadata -f 'ba' -x --audio-format mp3 --audio-quality 0 --no-check-certificate "VIDEO_ID" -o "%(title)s.mp3"
```

<br>

# Shorten the MP3

If you download a track/mix that is too long, you can condense the track by "splicing" it and also add fade-in and fade-out in however many seconds you choose. The code below is from the Github's readme, very simple to use!

```
from pydub import AudioSegment

# Tell PyDub what MP3 you want to splice
song = AudioSegment.from_mp3("FILE.mp3")

# Pydub love milliseconds
one_hour = 3600000  # 6300000 milliseconds is 1 hour

# Get first hour of song
first_hour = song[:one_hour]

# Fade in and out, 2 seconds
final_song = first_hour.fade_in(2000).fade_out(2000)

# Export back to MP3
final_song.export("SONGFILE.mp3", format="mp3")
```

<br>

# Final Thoughts

You can very easily take the tools above and do a whole lot more. For example, find a YouTube playlist of some cool songs or mixes and feed them into YT-DLP. Either enjoy the MP3s you get from that or shorten each track down to the first hour. Enjoy!
