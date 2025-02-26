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
-o ~/var/services/video/YouTube2/%(title)s.%(ext)s
```

# run
```
./yt-dlp.sh https://www.youtube.com/watch?v=zlq0CUtkOSI
```


