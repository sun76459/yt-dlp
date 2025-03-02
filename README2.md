# installation
```
/usr/local/bin/python3.9 -m venv venv
. venv/bin/activate

python --version
Python 3.9.14 (Good!)

python3 --version
Python 3.9.14
```

# options in configuration file
```
/volume1/repos/yt-dlp/yt-dlp.conf

# Always extract audio
-x
--audio-format mp3
--ffmpeg-location /usr/local/bin/ffmpeg7

# Do not copy the mtime
--no-mtime

# Output file path and name
-o "/volume1/video/tmp/%(title)s.%(ext)s"
-o "/volume1/video/tmp/%(playlist)s/%(playlist_index)s - %(title)s.%(ext)s"
-o "/volume1/video/tmp/%(playlist_id)s/%(playlist_index)s - %(title)100s.%(ext)s"


```
# to ignore config file
```
--ignore-config
```

# run
```
# download
./yt-dlp.sh https://www.youtube.com/watch?v=zlq0CUtkOSI

# download mp3 file
./yt-dlp.sh --ignore-config -x --no-mtime --audio-format mp3 --ffmpeg-location /usr/local/bin/ffmpeg7 -o /volume1/video/tmp/%(title)s.%(ext)s https://www.youtube.com/watch?v=zlq0CUtkOSI

# download a playlist
./yt-dlp.sh --ignore-config -x --no-mtime --audio-format mp3 --ffmpeg-location /usr/local/bin/ffmpeg7 -o "/volume1/video/tmp/%(playlist_id)s/%(playlist_index)s - %(title)s.%(ext)s" --trim-filenames 100 "https://www.youtube.com/watch?v=tNYiMxHbcE4&list=PL_IzBVwc567ZMQNUOSJTpM-kwz3vStH90"
```

