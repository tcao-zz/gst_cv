This code applies filters to input images in OpenCV, and
streams the processed images to a host in GStreamer/RTP.

It runs on Beaglebone White or Black, and should run on
any platforms with the following package installed:
gstreamer 0.10 and OpenCV

The host should have gstreamer installed.

To start the gstreamer at the host as a client or data sink, run:
gst-launch udpsrc port=5000 ! theoradec ! ffmpegcolorspace ! ximagesink
This works on Mac, and it should work on Linux or Windows with little tweak.

To start the image processing and streaming, compile and run the code as:
./gst_appsrc --input=beagle.jpg --host=192.168.0.175


