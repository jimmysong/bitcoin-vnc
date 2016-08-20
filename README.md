[![Docker Pulls](https://img.shields.io/docker/pulls/jimmysong76/bitcoin-vnc.svg)](https://hub.docker.com/r/jimmysong76/bitcoin-vnc/)
[![Docker Stars](https://img.shields.io/docker/stars/jimmysong76/bitcoin-vnc.svg)](https://hub.docker.com/r/jimmysong76/bitcoin-vnc/)

bitcoin-vnc
===
Simple VNC-connectable docker container that uses:

 * Ubuntu Core 14.04
 * LXDE desktop
 * TightVNC server
 * Bitcoin 0.12.1

Build
-----
Include password.txt with the password for TightVNC (by default this is "password"). This must be at least 8 characters and is truncated if longer.

Usage
-----
You can build with

    (host) $ docker build -t bitcoin-vnc .

Create and start with

    (host) $ id
    uid=XXXX(YYYY) gid=ZZZZ(YYYY)
    (host) $ docker create --name=bitcoin -p 5901:5901 -v <bitcoin dir>:/bitcoin -e PUID=XXXX -e PGID=ZZZZ bitcoin-vnc
    (host) $ docker start bitcoin

You can connect to the vnc server using at SERVER_NAME:5901 using the password from password.txt (default is "password") where SERVER_NAME is the docker container host's name or IP.

Within the container, you can query bitcoin-cli like this:

    (container) $ bitcoin-cli -datadir=/bitcoin getinfo


Credit
------

Based off of the docker image [kaixhin/vnc](https://github.com/Kaixhin/dockerfiles/tree/master/vnc).