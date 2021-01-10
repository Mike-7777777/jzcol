# jzcol
Jazzzzzzzzzz all the time.



测试链接

youtube.com/watch?v=Dx5qFachd3A

https://github.com/ytdl-org/youtube-dl

https://github.com/streamlink/streamlink

youtube-dl -f best -g youtube.com/watch?v=Dx5qFachd3A

streamlink -o output.txt https://www.youtube.com/watch?v=DSGyEsJ17cI best

streamlink https://www.youtube.com/watch?v=DSGyEsJ17cI



后处理 -x 将视频转为纯音频(需要ffmpeg) 



https://www.youtube.com/watch?v=DSGyEsJ17cI

streamlink  www.youtube.com/watch?v=Dx5qFachd3A

https://www.youtube.com/watch?v=Dx5qFachd3A

```
streamlink -o file.mp4 youtube.com/watch?v=DSGyEsJ17cI best
```

```
streamlink -o file.mp4 https://www.youtube.com/watch?v=Dx5qFachd3A best
```

存储流为ogg格式

```
streamlink -p "C:\Program Files\VideoLAN\VLC\vlc.exe" -a ":sout=#transcode{{vcodec=none,acodec=vorb,ab=256,channels=2,samplerate=48000,scodec=none}}:rtp{{sdp=rtsp://:8554/v}} :no-sout-all :sout-keep" https://www.youtube.com/watch?v=QOOLxYfoz88 best
```

在VLC - 1中媒体-流, 源由streamlink提供, 选择RTSP方式, 路径为/v,端口为8554,不激活转码配置文件为vorbisOGG.

在VLC - 2 中播放, 地址为rtsp://192.168.0.3:8554/v

以下代码本地测试成功

```
vlc "D:\youtube-dl\lofi.m4a" :sout=#transcode{vcodec=none,acodec=vorb,ab=256,channels=2,samplerate=48000,scodec=none}:rtp{sdp=rtsp://:8554/v} :no-sout-all :sout-keep
```

以下代码部署在服务器端



```
vlc -vvv file.mp4 --sout '#transcode{vcodec=none,acodec=vorb,ab=256,channels=2,samplerate=48000,scodec=none}:rtp{sdp=rtsp://:8554/v}'
```

rtsp://194.156.99.137:8554/v

```
cvlc file:///file.mp4 --sout '#transcode{vcodec=none,acodec=vorb,ab=256,channels=2,samplerate=48000,scodec=none}:rtp{sdp=rtsp://:8554/v}'
```

