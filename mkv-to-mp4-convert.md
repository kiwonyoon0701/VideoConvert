```
MYDATE=`date "+%Y-%m-%d-%H-%M-%S"`
SOURCE_FILE=4.mkv
ffmpeg -i $SOURCE_FILE -vcodec copy -acodec copy $MYDATE.mp4
```
