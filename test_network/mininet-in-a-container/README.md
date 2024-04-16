

install https://www.xquartz.org

run xhost +

run the command 
```
docker run -it --rm --privileged -e DISPLAY=host.docker.internal:0 \
-v /tmp/.X11-unix:/tmp/.X11-unix \
-v /lib/modules:/lib/modules \
-v $(pwd)/pcap_files:/pcap_files \
--name=mininet \
mininet
```

 sudo mn --controller=remote,ip={ip_address},port=6633



# Mininet in a container

A Docker image for [Mininet](http://mininet.org/), based on this one: https://github.com/iwaseyusuke/docker-mininet.

It works in Linux-based systems (e.g., Ubuntu native or virtual via VirtualBox); it also works with MacOS.

It basically adds these elements:
* wireshark-qt
* wget
* python-tk (for miniedit.py)
* git

and the download of the Mininet source code:
* https://github.com/mininet/mininet


## Docker *build* Command
To build the image locally you can use:

```bash
docker build -t mininet-in-a-container . 
```

### run command for a Unix machine:
```bash
docker run -it --rm --privileged -e DISPLAY \
             -v /tmp/.X11-unix:/tmp/.X11-unix \
             -v /lib/modules:/lib/modules \
             --name mininet mininet-in-a-container
```

### run command for MacOS: 
```bash
docker run -it --rm --privileged -e DISPLAY \
      --env="DISPLAY=host.docker.internal:0" \
      -v /tmp/.X11-unix:/tmp/.X11-unix:rw \
      -v /lib/modules:/lib/modules \
      --name mininet mininet-in-a-container
```




## Using the prebuilt image "pmanzoni/mininet-in-a-container"
Be careful. It was built on a M2-based machine!!!


### Use this command:
```bash
docker run -it --rm --privileged -e DISPLAY \
      -v /tmp/.X11-unix:/tmp/.X11-unix \
      -v /lib/modules:/lib/modules \
      --name mininet mininet-in-a-container
```

### For MacOS: 
```bash
docker run -it --rm --privileged -e DISPLAY \
      --env="DISPLAY=host.docker.internal:0" \
      -v /tmp/.X11-unix:/tmp/.X11-unix:rw \
      -v /lib/modules:/lib/modules \
      --name mininet mininet-in-a-container
```


