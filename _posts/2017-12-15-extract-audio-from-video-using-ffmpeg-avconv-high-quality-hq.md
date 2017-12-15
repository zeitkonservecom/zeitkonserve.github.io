`ffprobe video.mp4` or `avprobe video.mp4` tells, which audio format the video has.

According to this, just extract the audio to a file (file name extension must be according to the format):

```
for i in *.mp4;
    do avconv -i "$i" -vn -acodec copy "$i.aac";
done
```

Look into the output:

```
[...]
Stream #0:0(und): Audio: aac (LC) (mp4a / 0x6134706D), 44100 Hz, stereo, fl
tp, 125 kb/s (default)
    Metadata:
      handler_name    : SoundHandler
Stream mapping:
  Stream #0:1 -> #0:0 (copy)
[...]
```

ffmpeg/avconv will not convert the audio stream, but just save it in hq.
