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
-P "/volume1/video/tmp"
-o "%(title)s.%(ext)s"
-o "%(playlist)s/%(playlist_index)s - %(title)s.%(ext)s"
-o "%(playlist_id)s/%(playlist_index)s - %(title)100s.%(ext)s"


```
# to ignore config file
```
--ignore-config
```

# run
```
# download webm file
./yt-dlp.sh https://www.youtube.com/watch?v=zlq0CUtkOSI

# download opus file
./yt-dlp.sh -x https://www.youtube.com/watch?v=zlq0CUtkOSI

# download mp3 file (audio-quality 0=best, default is 5)
./yt-dlp.sh -x --audio-format mp3 --audio-quality 0 https://www.youtube.com/watch?v=zlq0CUtkOSI

# download mp4 file
./yt-dlp.sh -f mp4 https://www.youtube.com/watch?v=zlq0CUtkOSI

# download a playlist
./yt-dlp.sh -x --no-mtime --audio-format mp3 --ffmpeg-location /usr/local/bin/ffmpeg7 -o "%(playlist_id)s/%(playlist_index)s - %(title)s.%(ext)s" --trim-filenames 100 "https://www.youtube.com/watch?v=tNYiMxHbcE4&list=PL_IzBVwc567ZMQNUOSJTpM-kwz3vStH90"
```

