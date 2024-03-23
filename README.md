# Download a full playlist from YouTube at once.

## Modules that are needed for this program
- In python 
```
pip install pytube
```
---------- or -----------
```
pip3 install pytube
```

- For video audio mixer 
  - Mac Os.
  ```
   brew install ffmpeg
  ```
  - Linux 
  ```
  sudo apt install ffmpeg
  ffmpeg -version
  ```
 ### Import these modules

 ```python
import os
import re
from pytube import Playlist, YouTube
```

### For download videos from YouTube without audio
```python
video_stream = video_streams.first()
video_name = video_stream.default_filename
print(f"Downloading video for {video_name} in {resolution}")
video_stream.download(filename="video.mp4")
```


### Download audio only
```python
audio_stream = video.streams.get_audio_only()
print(f"Downloading audio for {video_name}")
audio_stream.download(filename="audio.mp4")
```

### For mixing audio and video
```python
os.system("ffmpeg -y -i video.mp4 -i audio.mp4 -c:v copy -c:a aac final.mp4 -loglevel quiet -stats")
os.rename("final.mp4", video_path)
os.remove("video.mp4")
os.remove("audio.mp4")
```
