#run xserver
xhost +local:docker

#XSOCK=/tmp/.X11-unix
#XAUTH=/tmp/.docker.xauth
#xauth nlist $DISPLAY | sed -e 's/^..../ffff/' | xauth -f $XAUTH nmerge -

docker-compose -f docker-compose-code.yml up

#stop xserver
xhost -local:docker