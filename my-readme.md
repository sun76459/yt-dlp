# installation
```
/usr/local/bin/python3.9 -m venv venv
. venv/bin/activate

python --version
Python 3.9.14 (Good!)

python3 --version
Python 3.9.14
```

# configuration file
```
/volume1/repos/yt-dlp/yt-dlp.conf
# Lines starting with # are comments

# Always extract audio
-x

# Do not copy the mtime
--no-mtime

# Use this proxy
#--proxy 127.0.0.1:3128

# Save all videos under YouTube directory in your home directory
-o /var/services/video/YouTube2/%(title)s.%(ext)s
-o "/var/services/video/YouTube2/%(playlist)s/%(playlist_index)s - %(title)s.%(ext)s"

```

# run
```
# download a list
./yt-dlp.sh "https://www.youtube.com/watch?v=tNYiMxHbcE4&list=PL_IzBVwc567ZMQNUOSJTpM-kwz3vStH90"

# download mp3 file. -x = extract audio, --audio-format is mp3 
./yt-dlp.sh https://www.youtube.com/watch?v=zlq0CUtkOSI -x --audio-format mp3

# ignore config file, download file to /volume1/downloads folder
./yt-dlp.sh https://www.youtube.com/watch?v=zlq0CUtkOSI -P /volume1/downloads --ignore-config --ffmpeg-location /usr/local/bin/ffmpeg7

# specify a config file, use mp3.conf config file
./yt-dlp.sh https://www.youtube.com/watch?v=zlq0CUtkOSI --config-location mp3.conf

```

