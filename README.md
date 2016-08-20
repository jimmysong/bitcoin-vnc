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

    ```bash
    $ docker build -t bitcoin .
    ```

Create and start with

    ```bash
    $ docker create --name=bitcoin -p 5901:5901 jimmysong76/bitcoin-vnc
    $ docker start bitcoin
    ```

You can connect to the vnc server using at <SERVER_NAME>:5901 using the password from password.txt (default is "password") where SERVER_NAME is the docker container host's name or IP.

Credit
------

Based off of kaixhin/vnc.