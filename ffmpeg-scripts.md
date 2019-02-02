#### Put two videos side by side
`ffmpeg -i left-video.mp4 -i right-video.mp4 -filter_complex hstack output.mp4`

#### To crop black borders, get the correct values first
`ffmpeg -i input-video.mp4 -t 1 -vf cropdetect -f null - 2>&1 | awk '/crop/ { print $NF }' | tail -1`

`ffmpeg -i input-video.mp4 -vf "crop=0:0:0:0" output.mp4`

#### Use the Mac FaceTime camera to take a picture
`ffmpeg -f avfoundation -video_size hd720 -framerate 30 -i "0" -vframes 1 output.jpg`