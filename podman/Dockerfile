FROM python:3.9.16-bullseye

RUN apt update
RUN apt install -y \
  libasound2-dev \
  libjack-dev \
  gobject-introspection \
  libgirepository1.0-dev \
  libqt5core5a \
  qtwayland5 \
  qt5-gtk-platformtheme \
  python3-gst-1.0 \
  gstreamer1.0-plugins-good \
  gstreamer1.0-plugins-bad

RUN echo "deb http://ftp.de.debian.org/debian bullseye-backports main" >> /etc/apt/sources.list
RUN apt update && \
    apt -y dist-upgrade && \
    apt -y install -t bullseye-backports pipewire pipewire-jack
RUN cp /usr/share/doc/pipewire/examples/ld.so.conf.d/pipewire-jack-*.conf /etc/ld.so.conf.d/
RUN ldconfig
