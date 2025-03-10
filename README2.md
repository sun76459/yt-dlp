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
# download video (default: webm)
./yt-dlp.sh https://www.youtube.com/watch?v=zlq0CUtkOSI

# download audio (default: opus)
./yt-dlp.sh https://www.youtube.com/watch?v=zlq0CUtkOSI -x

# download video (mp4)
./yt-dlp.sh https://www.youtube.com/watch?v=zlq0CUtkOSI -f mp4

# download audio (m4a)
./yt-dlp.sh https://www.youtube.com/watch?v=zlq0CUtkOSI -f m4a

# download audio (mp3, need ffmpeg)
./yt-dlp.sh https://www.youtube.com/watch?v=zlq0CUtkOSI -x --audio-format mp3 --audio-quality 0

# list formats
./yt-dlp.sh https://www.youtube.com/watch?v=gMG_MR-ihis --list-formats

# limit the resolution to 720p
./yt-dlp.sh https://www.youtube.com/watch?v=zlq0CUtkOSI -f "bv*[ext=webm][height<=720]+ba[ext=webm]/b[ext=webm]"

# download playlist as webm, upto 720p
time ./yt-dlp.sh "https://www.youtube.com/watch?v=Lb8RjZGB0Us&list=PLkvG4EWPDB0m8u9tgBwBpU9oorJ1kDPgU" -f "bv*[ext=webm][height<=720]+ba[ext=webm]/b[ext=webm]" -o "%(playlist_id)s/%(playlist_index)s - %(title)s.%(ext)s"

# download playlist as mp4, avoid vp9 (iOS does not support vp9), upto 720p, 凡人歌, ^= means starts with
time ./yt-dlp.sh "https://www.youtube.com/watch?v=Lb8RjZGB0Us&list=PLkvG4EWPDB0m8u9tgBwBpU9oorJ1kDPgU" -f "bv*[vcodec^=avc1][height<=720]+ba[ext=m4a]/b[ext=mp4]" --merge-output-format mp4 -o "%(playlist_id)s/%(playlist_index)s - %(title)s.%(ext)s"


# download playlist as webm, upto 1080p
time ./yt-dlp.sh "https://www.youtube.com/watch?v=t8YD27LZkiQ&list=PLQqbdnAgoRmZGKpEYTew9llwAjkP6wNLr" -f "bv*[ext=webm][height<=1080]+ba[ext=webm]/b[ext=webm]" -o "%(playlist_id)s/%(playlist_index)s - %(title)s.%(ext)s"

# download a playlist to m4a files
./yt-dlp.sh -f "ba[ext=m4a]" -o "%(playlist_id)s/%(playlist_index)s - %(title)s.%(ext)s" "https://www.youtube.com/watch?v=tNYiMxHbcE4&list=PL_IzBVwc567ZMQNUOSJTpM-kwz3vStH90"
```
