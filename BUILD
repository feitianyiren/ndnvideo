Tested on:
- Linux OpenSuSE & Ubuntu
- MacOS X

better documentation pending, meanwhile for the early adopters:

Dependencies & installing:

- ccnx (includes ccnr)
  If you plan streaming and ccnr crashes when it reaches size around 2GB
  create file csrc/conf/local.mk with:
  PLATCFLAGS= -O2 -D_FILE_OFFSET_BITS=64 -fPIC

- pyccn (git://github.com/remap/PyCCN.git)
- ndnvideo (play_latest branch - git://github.com/remap/ndnvideo.git)

- gstreamer 0.10 - will NOT WORK with 1.0... must restrict packages to 0.10 for ndnvideo compatibilty. 

from there, platform specific, incomplete list below:


ubuntu:
gstreamer0.10-plugins-ugly (for x264 encoding)
python-gst0.10-dev (for gst-python)
gstreamer0.10-ffmpeg

OSX:

Install gstreamer & plugins view MacPorts:

sudo port install gst-ffmpeg gst-plugins-bad gst-plugins-base gst-plugins-gl gst-plugins-gl gst-plugins-gl gst-plugins-good gst-plugins-ugly gst-rtsp-server gstreamer py27-gst-python

well - that use to work, some point in 2013 it changed to:

sudo port install gstreamer010-gst-ffmpeg gstreamer010-gst-plugins-bad gstreamer010-gst-plugins-base gstreamer010-gst-plugins-gl gstreamer010-gst-plugins-gl gstreamer010-gst-plugins-gl gstreamer010-gst-plugins-good gstreamer010-gst-plugins-ugly gstreamer010-gst-rtsp gstreamer010 py27-gst-python py27-pygtk py-pygtk

- install PyCCN


testing:

To make sure gst works you can try:

gst-launch videotestsrc ! ximagesink
gst-launch v4l2src ! ximagesink
gst-launch v4l2src ! x264enc ! ffdec_h264 ! ximagesink


To check that python bindings are available do:

$ python
import pygst


Troubleshooting:

if you get "No module named pygtk" then this most likely means that the python you're using is the one that
comes with MacOS X. Unfortunately the Mac Ports packages aren't visible
by default to that python, you could probably set up PYTHONPATH to point
there but probably is easier to just use the python from macports.

