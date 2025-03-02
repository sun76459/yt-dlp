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

# Use mp4 (default would be webm)
-f "bestvideo[ext=mp4]+bestaudio[ext!=opus]/best[ext=mp4]"

```
# to ignore config file
```
--ignore-config
```

# run
```
# download mp4 file
./yt-dlp.sh https://www.youtube.com/watch?v=zlq0CUtkOSI

# download audio file (because the default video is mp4, the default audio is m4a, it does not need ffmpeg)
./yt-dlp.sh -x https://www.youtube.com/watch?v=zlq0CUtkOSI

# download mp3 file (audio-quality 0=best, default is 5. ffmpeg will be used to convert m4a to mp3. slow!)
./yt-dlp.sh -x --audio-format mp3 --audio-quality 0 https://www.youtube.com/watch?v=zlq0CUtkOSI

# download a playlist to mp3 files
./yt-dlp.sh -x --audio-format mp3 --audio-quality 0 -o "%(playlist_id)s/%(playlist_index)s - %(title)s.%(ext)s" --trim-filenames 100 "https://www.youtube.com/watch?v=tNYiMxHbcE4&list=PL_IzBVwc567ZMQNUOSJTpM-kwz3vStH90"
```

