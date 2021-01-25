FROM debian:buster

RUN cat /etc/apt/sources.list |sed "s/deb\.debian\.org/mirrors\.tuna\.tsinghua\.edu\.cn/g" > /etc/apt/sources.list.tmp
RUN cat /etc/apt/sources.list.tmp |sed "s/security\.debian\.org/mirrors\.tuna\.tsinghua\.edu\.cn/g" > /etc/apt/sources.list
RUN rm /etc/apt/sources.list.tmp
# Install git, supervisor, VNC, & X11 packages
RUN set -ex; \
    apt-get update; \
    apt-get install -y \
      bash \
      fluxbox \
      git \
      net-tools \
      novnc \
      supervisor \
      x11vnc \
      xterm \
      xvfb

# Setup demo environment variables
ENV HOME=/root \
    DEBIAN_FRONTEND=noninteractive \
    LANG=en_US.UTF-8 \
    LANGUAGE=en_US.UTF-8 \
    LC_ALL=C.UTF-8 \
    DISPLAY=:0.0 \
    DISPLAY_WIDTH=1024 \
    DISPLAY_HEIGHT=768 \
    RUN_XTERM=yes \
    RUN_FLUXBOX=yes
COPY . /app
CMD ["/app/entrypoint.sh"]
EXPOSE 8080
