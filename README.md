# sampleMp3s

Further tools for building adventhymnals.

### Spliting an mp3 file using vlc
```bash
dir=whispering;interval=2;x=0; mkdir -p "$dir";while [ $x -le $(bc -l <<<"2*60 + 1") ]; do startTime=$x;let x+=interval;stopTime=$x;echo "$startTime"-$stopTime;let x++ ; cvlc Whispering\ HopeTukSDA\ Church\ ChoirLyrics\ Video.mp3 --sout "#duplicate{dst=std{access=file,mux=raw,dst=$dir/$startTime.mp3}" --start-time $startTime --stop-time $stopTime vlc://quit; done
```
