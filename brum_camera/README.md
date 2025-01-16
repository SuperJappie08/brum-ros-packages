# Brum Camera Package
The Camera on Brum is an Raspberry Pi Camera module V2 connected to the CSI port of a Raspberry Pi 5 running Ubuntu 24.04 (Desktop, for now).

## Setup steps:
1. Build [raspberrypi/libcamera](https://github.com/raspberrypi/libcamera) (Instructions [here](https://www.raspberrypi.com/documentation/computers/camera_software.html#building-libcamera))
1. (assuming plugin path is empty)`export GST_PLUGIN_PATH=/usr/local/lib/aarch64-linux-gnu/gstreamer-1.0`
2. ?Opt? Build `rpicam-apps` (Still image works, rest not so much?)

Test command `gst-launch-1.0 libcamerasrc ! video/x-raw,colorimetry=bt709,format=NV12,width=1600,height=1200,framerate=30/1 ! videoflip method=rotate-180 ! queue ! glimagesink`

# License
The Package is licensed under the MIT License.
