Copy everything inside this template folder into your target directory

Just use this command to back-up YouTube videos:
```
youtube-dl.exe --config-location archive.conf [Your video/playlist/channel URL]
```

To back-up YouTube-native subtitles (srv3), run this commmand using the same URL:
```
youtube-dl --download-archive srv3.tracker --skip-download --sub-format srv3 --all-subs --write-sub [URL]
```