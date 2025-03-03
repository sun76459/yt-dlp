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

# Do not copy the mtime
--no-mtime

# Output folder
-P /volume1/video/tmp

# Output filename
-o %(title)s.%(ext)s

--ffmpeg-location /usr/local/bin/ffmpeg7

# Avoid long file name
--trim-filenames 100

```
# to ignore config file
```
--ignore-config
```

# run
```
# download webm file (default)
./yt-dlp.sh https://www.youtube.com/watch?v=zlq0CUtkOSI

# download mp4 file
./yt-dlp.sh https://www.youtube.com/watch?v=zlq0CUtkOSI -f mp4

# download opus file (default)
./yt-dlp.sh https://www.youtube.com/watch?v=zlq0CUtkOSI -x

# download mp3 file
./yt-dlp.sh https://www.youtube.com/watch?v=zlq0CUtkOSI -x --audio-format mp3 --audio-quality 0

# download a playlist to mp3 files
./yt-dlp.sh -x -o "%(playlist_id)s/%(playlist_index)s - %(title)s.%(ext)s" --trim-filenames 100 "https://www.youtube.com/watch?v=tNYiMxHbcE4&list=PL_IzBVwc567ZMQNUOSJTpM-kwz3vStH90"
```

