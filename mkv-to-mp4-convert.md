**Install ffmpeg**

```
ubuntu@ip-10-100-1-108:/home/ubuntu/stage> sudo apt-get install ffmpeg
```


**convert.sh**
```
ubuntu@ip-10-100-1-108:/home/ubuntu/stage> cat convert.sh
#!/bin/bash
if [ $# -ne 1 ]
then
	echo 'Usage : convert.sh SOURCE_FILE_NAME'
	exit
fi
MYDATE=`date "+%Y-%m-%d-%H-%M-%S"`
SOURCE_FILE=$1
ffmpeg -i $SOURCE_FILE -vcodec copy -acodec copy $MYDATE.mp4

ubuntu@ip-10-100-1-108:/home/ubuntu/stage> ./convert.sh 4.mkv
ffmpeg version 3.4.8-0ubuntu0.2 Copyright (c) 2000-2020 the FFmpeg developers
  built with gcc 7 (Ubuntu 7.5.0-3ubuntu1~18.04)
  configuration: --prefix=/usr --extra-version=0ubuntu0.2 --toolchain=hardened --libdir=/usr/lib/x86_64-linux-gnu --incdir=/usr/include/x86_64-linux-gnu --enable-gpl --disable-stripping --enable-avresample --enable-avisynth --enable-gnutls --enable-ladspa --enable-libass --enable-libbluray --enable-libbs2b --enable-libcaca --enable-libcdio --enable-libflite --enable-libfontconfig --enable-libfreetype --enable-libfribidi --enable-libgme --enable-libgsm --enable-libmp3lame --enable-libmysofa --enable-libopenjpeg --enable-libopenmpt --enable-libopus --enable-libpulse --enable-librubberband --enable-librsvg --enable-libshine --enable-libsnappy --enable-libsoxr --enable-libspeex --enable-libssh --enable-libtheora --enable-libtwolame --enable-libvorbis --enable-libvpx --enable-libwavpack --enable-libwebp --enable-libx265 --enable-libxml2 --enable-libxvid --enable-libzmq --enable-libzvbi --enable-omx --enable-openal --enable-opengl --enable-sdl2 --enable-libdc1394 --enable-libdrm --enable-libiec61883 --enable-chromaprint --enable-frei0r --enable-libopencv --enable-libx264 --enable-shared
  libavutil      55. 78.100 / 55. 78.100
  libavcodec     57.107.100 / 57.107.100
  libavformat    57. 83.100 / 57. 83.100
  libavdevice    57. 10.100 / 57. 10.100
  libavfilter     6.107.100 /  6.107.100
  libavresample   3.  7.  0 /  3.  7.  0
  libswscale      4.  8.100 /  4.  8.100
  libswresample   2.  9.100 /  2.  9.100
  libpostproc    54.  7.100 / 54.  7.100
Input #0, matroska,webm, from '4.mkv':
  Metadata:
    title           : 1022_230000_CH107-1_HD TVN.tp
    encoder         : Lavf52.56.0
  Duration: 01:23:23.56, start: 0.000000, bitrate: 3974 kb/s
    Stream #0:0: Video: h264 (Constrained Baseline) (H264 / 0x34363248), yuv420p(progressive), 1280x720 [SAR 1:1 DAR 16:9], 15.17 fps, 59.94 tbr, 1k tbn, 29.97 tbc (default)
    Stream #0:1: Audio: ac3, 48000 Hz, stereo, fltp, 128 kb/s (default)
[mp4 @ 0x5565d75bce00] track 1: codec frame size is not set
Output #0, mp4, to '2020-09-09-14-06-27.mp4':
  Metadata:
    title           : 1022_230000_CH107-1_HD TVN.tp
    encoder         : Lavf57.83.100
    Stream #0:0: Video: h264 (Constrained Baseline) (avc1 / 0x31637661), yuv420p(progressive), 1280x720 [SAR 1:1 DAR 16:9], q=2-31, 15.17 fps, 59.94 tbr, 16k tbn, 1k tbc (default)
    Stream #0:1: Audio: ac3 (ac-3 / 0x332D6361), 48000 Hz, stereo, fltp, 128 kb/s (default)
Stream mapping:
  Stream #0:0 -> #0:0 (copy)
  Stream #0:1 -> #0:1 (copy)
Press [q] to stop, [?] for help
[mp4 @ 0x5565d75bce00] Timestamps are unset in a packet for stream 0. This is deprecated and will stop working in the future. Fix your code to set the timestamps properly
[mp4 @ 0x5565d75bce00] Non-monotonous DTS in output stream 0:0; previous: 5344, current: 4272; changing to 5345. This may result in incorrect timestamps in the output file.
[mp4 @ 0x5565d75bce00] Non-monotonous DTS in output stream 0:0; previous: 5345, current: 3472; changing to 5346. This may result in incorrect timestamps in the output file.
[mp4 @ 0x5565d75bce00] Non-monotonous DTS in output stream 0:0; previous: 5346, current: 4000; changing to 5347. This may result in incorrect timestamps in the output file.
[mp4 @ 0x5565d75bce00] Non-monotonous DTS in output stream 0:0; previous: 5347, current: 4544; changing to 5348. This may result in incorrect timestamps in the output file.
[mp4 @ 0x5565d75bce00] Non-monotonous DTS in output stream 0:0; previous: 5348, current: 5072; changing to 5349. This may result in incorrect timestamps in the output file.
frame=149955 fps=32151 q=-1.0 Lsize= 2427908kB time=01:23:23.53 bitrate=3975.1kbits/s speed=1.07e+03x
video:2346912kB audio:78175kB subtitle:0kB other streams:0kB global headers:0kB muxing overhead: 0.116322%

ubuntu@ip-10-100-1-108:/home/ubuntu/stage> ls -alrt *.mp4
-rw-rw-r-- 1 ubuntu ubuntu 1394898661 Sep  9 13:55 2.mp4
-rw-rw-r-- 1 ubuntu ubuntu 2486177874 Sep  9 14:06 2020-09-09-14-06-27.mp4
```
